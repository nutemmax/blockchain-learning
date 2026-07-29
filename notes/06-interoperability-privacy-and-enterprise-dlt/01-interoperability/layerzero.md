# LayerZero

## Scope

LayerZero is a general cross-chain messaging protocol. Applications use common
Endpoint contracts to dispatch messages, choose verification services, and
execute verified messages on destination chains. LayerZero does not make all
chains share consensus and it is not itself an asset custodian. An application's
security depends heavily on its configured message libraries, Decentralized
Verifier Networks, confirmation settings, contracts, and administrator powers.

This note focuses on LayerZero V2. Earlier versions used different terminology
and architecture; analysis should not mix them.

## 1. Problem and Design Philosophy

Cross-chain applications need a stable interface while chains and verification
methods evolve. LayerZero separates five layers:

1. application business logic;
2. immutable Endpoint interface and messaging channels;
3. configurable Message Libraries;
4. verification by Decentralized Verifier Networks, or DVNs; and
5. delivery by Executors.

The intended design is **application-owned security**. Rather than one mandatory
validator set securing every message, each omnichain application selects a
verification rule for each pathway.

This flexibility has two consequences:

- applications can combine independent verification systems and change them;
- users cannot infer security from the LayerZero name alone.

## 2. Core Components

### 2.1 Omnichain applications

An OApp is an application with contracts or programs on multiple chains. A
source OApp sends a payload; a destination OApp receives and interprets it.

The application controls:

- trusted peers on remote chains;
- DVN selection and thresholds;
- required source confirmations;
- Message Library;
- Executor and gas options;
- ordering policy;
- business logic; and
- administrative controls.

An incorrectly configured peer can accept messages from an attacker's contract
even if the transport verifies them perfectly.

### 2.2 Endpoint V2

Each supported chain has an Endpoint contract that exposes a common send and
receive interface. The Endpoint:

- identifies chains with Endpoint IDs;
- defines channels between source and destination applications;
- tracks per-channel nonces;
- delegates packet creation and verification to Message Libraries;
- records verified payload hashes;
- enforces exactly-once receipt at the channel level; and
- invokes the destination OApp.

LayerZero describes the core Endpoint interface as immutable and permissionless.
Configurable libraries and workers provide adaptability around that stable
interface.

### 2.3 Channels

A channel is identified by:

- source OApp;
- source Endpoint ID;
- destination Endpoint ID; and
- destination OApp.

Each channel maintains independent nonces. High traffic in one pathway therefore
need not block another unrelated pathway.

### 2.4 Message Libraries

A Message Library packages messages on the source and verifies them on the
destination. Libraries are registered with the Endpoint, and OApps select send
and receive libraries by pathway.

The Ultra Light Node, or ULN, library is a push-messaging design that coordinates
DVNs. Other libraries can implement different verification or read models.

Library migration needs care. Send and receive sides can change at different
times, so grace periods and compatibility rules must prevent messages from being
lost or accepted under unintended security settings.

### 2.5 DVNs

A DVN is an independent verification service. It observes source-chain events
and submits verification of a packet hash to the destination Message Library.
A DVN can use:

- its own committee;
- a native bridge;
- a zero-knowledge proof;
- a light client;
- another middlechain; or
- a specialized institutional verification process.

The protocol standardizes how verifications are combined; it does not require
every DVN to use the same internal trust model.

### 2.6 Executors

An Executor delivers a verified message by calling the destination Endpoint with
the required gas and options. Verification and execution are separate.

The designated Executor is a convenience service rather than the root of message
authenticity. LayerZero V2 permits permissionless execution after verification,
and applications or users can execute manually. A failed or censoring Executor
should delay delivery, not forge a message.

## 3. End-to-End Message Flow

```mermaid
sequenceDiagram
    participant U as "User"
    participant SO as "Source OApp"
    participant SE as "Source Endpoint"
    participant D as "Configured DVNs"
    participant EX as "Executor"
    participant DE as "Destination Endpoint"
    participant DO as "Destination OApp"
    U->>SO: Call cross-chain action
    SO->>SE: send(destination, receiver, payload, options)
    SE-->>D: Emit packet and assign verification jobs
    SE-->>EX: Assign execution job
    D->>D: Observe source and wait for confirmations
    D->>DE: Submit payload-hash verifications
    DE->>DE: Threshold met; commit verified packet
    EX->>DE: Deliver payload with destination gas
    DE->>DO: lzReceive(origin, ID, payload)
    DO->>DO: Validate peer and execute business logic
```

### 3.1 Dispatch

The source OApp calls the Endpoint with:

- destination Endpoint ID;
- receiver address;
- arbitrary payload;
- execution options; and
- fee payment choice.

The Endpoint assigns a per-channel nonce, constructs a standardized packet, and
emits events for configured workers.

### 3.2 Verification

Each configured DVN observes the packet and waits for the required confirmations.
It submits a verification tied to the packet header and payload hash on the
destination.

The receive library checks whether the OApp's required and optional DVN rule is
satisfied. It then commits the verified payload hash to the destination channel.

### 3.3 Execution

An Executor or another caller supplies the original payload. The Endpoint checks
it against the committed hash, marks the message received, and calls the
destination OApp. The OApp authenticates the origin and applies its own logic.

Verification can succeed while execution fails. Applications need retryable
handling, adequate gas, and idempotent business logic.

## 4. The X-of-Y-of-N Security Rule

An OApp can configure:

- a set of **required DVNs**, all of which must verify;
- a set of **optional DVNs**; and
- an optional threshold specifying how many optional DVNs must verify.

For example:

```text
Required DVNs: A and B
Optional DVNs: C, D, and E
Optional threshold: 2

Message accepted only if:
A verifies
and B verifies
and any 2 of C, D, and E verify
```

This is more expressive than a simple threshold because specific verifiers can
be mandatory.

### 4.1 Security interpretation

For a false message to pass, an attacker must defeat the configured combination,
subject to implementation and administration correctness. If required DVN A and
any two optional DVNs are compromised but required DVN B remains honest, the
false message should not verify.

For a valid message to remain unavailable, enough configured DVNs need only stop
signing. Thus:

- safety improves with independent required verifiers;
- liveness becomes harder as more services are mandatory; and
- correlation matters more than nominal count.

Three DVNs running the same software, cloud, keys, and data source may fail
together.

### 4.2 Default configuration risk

Endpoints and libraries can expose defaults, but an OApp's owner is responsible
for its actual pathways. Security analysis should retrieve live onchain
configuration for both send and receive directions. Documentation examples do
not prove deployed settings.

## 5. Finality and Confirmations

Each pathway specifies how many source confirmations DVNs should wait. The
correct value depends on:

- source consensus and economic finality;
- ordinary and exceptional reorganization depth;
- rollup batch and proof status;
- sequencer behavior;
- value at risk;
- destination reversibility; and
- latency requirements.

If a message is verified before its source transaction is stable, a source reorg
can remove the initiating event after the destination action has become final.
There is no automatic cross-chain rollback.

Different DVNs should interpret chain finality consistently. Configuration and
implementation mismatches can create common-mode failure even with several
verifiers.

## 6. Omnichain Token Standards

### 6.1 Omnichain Fungible Token

The OFT pattern extends a fungible token across chains while maintaining a
coordinated total supply. A common design debits or burns tokens on the source
and credits or mints on the destination after message verification.

```text
Global supply = sum of recognized supply on all connected chains
```

Implementations may use:

- direct burn and mint for a natively controlled token;
- lock and mint when an existing token cannot be burned;
- an adapter around an existing canonical token; or
- issuer-specific logic.

The token issuer or contracts retain supply-control authority. LayerZero
transports the authorization message; it does not guarantee the economic backing
of the token.

### 6.2 Shared decimals and amount normalization

Chains and token programs can use different decimal precision. OFT contracts
normalize amounts into shared decimals for messages. Very small residual amounts
may be removed or rounded according to implementation.

Developers must test:

- decimal conversion;
- maximum supply and integer bounds;
- fees and slippage;
- dust handling; and
- behavior across non-EVM chains.

### 6.3 Omnichain applications beyond tokens

OApps can coordinate:

- governance;
- rewards;
- NFTs;
- lending positions;
- stablecoin supply;
- cross-chain swaps;
- data reads; and
- account actions.

Arbitrary messaging expands both usefulness and blast radius. Destination calls
should use least privilege and validate every origin and parameter.

## 7. lzRead and Cross-Chain Data

LayerZero V2 includes a read-oriented model in which an application requests
historical or current state from other chains and receives a verified response.
The architecture again uses configurable verification and execution services.

Read results inherit assumptions about:

- block identification and finality;
- state-proof or DVN correctness;
- data encoding;
- consistency across several requested chains;
- response freshness; and
- the destination action taken from the result.

A verified old value can still be economically unsafe. Applications need
freshness and monotonicity checks.

## 8. Fees and Execution Options

A source user generally pays:

- source-chain gas;
- fees quoted for configured DVNs;
- Executor fee for destination gas and service; and
- sometimes application or asset fees.

Fees vary with destination gas, message size, options, and worker pricing.
Execution options can request:

- destination gas limits;
- native-token delivery;
- ordered execution;
- compose calls; or
- other supported behavior.

Underestimating destination gas can leave a verified message unexecuted.
Overly permissive gas or native drops can increase cost and attack surface.

## 9. Administration and Governance

LayerZero's immutable Endpoint does not make OApps immutable. Analyze:

- who owns the OApp;
- who sets peers and security configuration;
- whether contracts are upgradeable;
- delay and review for changes;
- emergency pause powers;
- token mint and burn roles;
- treasury and fee controls; and
- whether ownership is multisignature, governance, or a single key.

Configuration changes can weaken security without altering the Endpoint. A
compromised OApp owner might replace strong DVNs, set an attacker-controlled
remote peer, or upgrade mint logic.

Good practice includes:

- explicit pathway configuration;
- independent required DVNs;
- timelocked changes where feasible;
- onchain configuration monitoring;
- separate operational and emergency roles;
- rate limits and value caps;
- peer and contract-code verification; and
- tested migration and recovery procedures.

## 10. Failure Modes

### 10.1 False verification

Enough DVNs attest to a packet that did not validly finalize on the source. The
destination can execute an unauthorized action. Loss is bounded only by
application permissions, caps, and response speed.

### 10.2 Verification outage

One or more required DVNs stop. Messages remain pending. Redundant optional DVNs
do not restore liveness if a mandatory DVN is unavailable.

### 10.3 Executor failure

The configured Executor fails to deliver or supplies inadequate gas. Once
verified, another executor or user may deliver, but applications need operational
tools and monitoring.

### 10.4 Destination application failure

The payload is authentic but causes a revert or an unintended action because
business logic is wrong. Transport security cannot protect unsafe OApp code.

### 10.5 Misconfiguration

Wrong peers, confirmation counts, libraries, or DVN thresholds can invalidate
the assumed model. This is one of the most important risks because flexibility
makes configuration part of code-level security.

### 10.6 Chain incident

A chain halt, reorg, fork, or disputed upgrade creates ambiguity. Operators need
predefined policies for pausing messages, selecting canonical history, and
resuming without double processing.

### 10.7 Library migration failure

Source and destination use incompatible libraries or grace periods. Messages can
be stranded or verified under old assumptions.

## 11. LayerZero Compared with Other Models

| Property | LayerZero V2 | Fixed validator bridge | Light-client bridge |
|---|---|---|---|
| Verification | OApp-configured DVNs and libraries | One protocol committee | Destination verifies source consensus |
| Flexibility | High, per pathway | Low to moderate | Constrained by supported clients |
| User analysis | Must inspect live OApp configuration | Inspect committee and gateway | Inspect client and consensus implementation |
| Liveness | Depends on required DVNs and executors | Depends on committee and relayer | Depends on header updates and relayer |
| Heterogeneous chains | Broad through adapters and DVNs | Broad | Technically demanding |
| Main risk | Configuration and verifier correlation | Committee compromise | Client or consensus-verification bug |

LayerZero can include a light-client or ZK verifier as a DVN. The categories are
therefore composable rather than mutually exclusive.

## 12. Evaluation Checklist

For a specific LayerZero integration, capture:

1. protocol version and Endpoint addresses;
2. OApp and peer contract addresses on every chain;
3. ownership and upgradeability;
4. send and receive Message Libraries;
5. required and optional DVNs and threshold;
6. internal trust model of each DVN;
7. independence among DVNs;
8. required confirmations per pathway;
9. Executor and manual-execution path;
10. nonce, ordering, retry, and compose behavior;
11. token debit, credit, lock, burn, and mint logic;
12. decimal normalization and supply invariants;
13. caps, rate limits, pause, and recovery;
14. chain-fork and library-migration policy;
15. audits, testing, monitoring, and incidents;
16. fees under ordinary and stressed conditions; and
17. legal rights of any omnichain asset.

The answer "secured by LayerZero" is incomplete. A meaningful statement names
the pathway and exact verifier rule.

## 13. Key Takeaways

1. LayerZero is a messaging interface and coordination framework, not a shared
   consensus layer.
2. Endpoint V2 provides immutable entry and exit interfaces and per-channel
   message tracking.
3. Message Libraries make verification modular; DVNs perform verification and
   Executors perform delivery.
4. Each OApp selects required and optional DVNs, thresholds, and confirmations.
5. More verifiers can improve safety while reducing liveness; independence is
   more important than count.
6. OFT coordinates token supply across chains but does not establish asset
   backing or legal rights.
7. The OApp's peer configuration, upgrade keys, and business logic can be weaker
   than the transport.
8. Live onchain configuration must be inspected in both directions.
9. Asynchronous failure, retries, reorgs, and migrations require explicit
   application design.

## Related Notes

- [Blockchain Interoperability and Bridges](blockchain-interoperability-and-bridges.md)
- [Interoperability Protocols](interoperability-protocols.md)
- [Blockchain Architecture](../../02-blockchain-foundations/01-core-architecture/blockchain-architecture.md)
- [Smart Contracts, Virtual Machines, and Token Standards](../../02-blockchain-foundations/03-execution-and-applications/smart-contracts-virtual-machines-and-token-standards.md)
- [Stablecoin Issuers and Protocols](../../05-digital-money-and-tokenization/01-stablecoins/stablecoin-issuers-and-protocols.md)

## References

- LayerZero, [Introduction](https://docs.layerzero.network/v2/home/intro)
- LayerZero, [Protocol architecture](https://docs.layerzero.network/v2/concepts/layerzero-protocol-architecture)
- LayerZero, [Protocol overview](https://docs.layerzero.network/v2/concepts/protocol/protocol-overview)
- LayerZero, [Endpoint](https://docs.layerzero.network/v2/concepts/protocol/layerzero-endpoint)
- LayerZero, [Message Libraries](https://docs.layerzero.network/v2/concepts/protocol/message-library)
- LayerZero, [DVN overview](https://docs.layerzero.network/v2/workers/off-chain/dvn-overview)
- LayerZero, [Verification and execution services](https://docs.layerzero.network/v2/concepts/verification-execution-services)
- LayerZero, [OApp technical reference](https://docs.layerzero.network/v2/developers/evm/oapp/overview)
- LayerZero, [OFT technical reference](https://docs.layerzero.network/v2/developers/evm/oft/quickstart)
- LayerZero, [Security stack](https://docs.layerzero.network/v2/concepts/modular-security/security-stack-dvns)
- LayerZero, [LayerZero V2 whitepaper](https://layerzero.network/publications/LayerZero_Whitepaper_V2.1.0.pdf)
- LayerZero Labs, [Protocol source code](https://github.com/LayerZero-Labs/LayerZero-v2)

