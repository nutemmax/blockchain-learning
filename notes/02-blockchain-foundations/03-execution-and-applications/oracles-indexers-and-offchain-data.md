# Oracles, Indexers, And Offchain Data

Blockchains are deterministic systems: validating nodes must derive the same
state from the same accepted inputs. A contract cannot independently fetch an
HTTP API, inspect a bank database, or know a court judgment because nodes could
receive different answers. Oracles bring external facts or computation into the
consensus state. Indexers transform blockchain data into forms applications can
query efficiently.

Both cross a trust boundary. An oracle can make false data authoritative
onchain; an indexer can show users an incorrect view even when the chain itself
is correct.

## The Oracle Problem

A blockchain can verify:

- transaction signatures;
- state-transition rules;
- cryptographic proofs;
- prior onchain data.

It cannot natively verify that:

- ETH traded at a particular USD price on external venues;
- a company defaulted;
- a shipment arrived;
- reserves exist in a bank account;
- an election or sporting event ended with a given result.

The oracle problem is how to import such claims with acceptable:

- correctness;
- availability;
- freshness;
- manipulation resistance;
- accountability;
- cost.

Cryptographic authentication proves that a source signed data, not that the
source measured reality correctly.

## Oracle Categories

### Input Oracle

Brings information onchain: prices, rates, weather, identity status, event
outcomes, reserves.

### Output Oracle

Triggers or informs an external system from onchain activity: bank payment,
shipment release, notification, or IoT control.

### Computation Oracle

Performs expensive or private computation offchain and returns a result or
proof.

### Cross-Chain Oracle

Reports state from one chain to another. This is commonly called a bridge or
interoperability protocol and adds source-finality and message-verification
assumptions.

### Human Oracle

Designated experts, arbitrators, voters, or governance determine subjective or
disputed outcomes.

## Delivery Models

### Push Feed

Reporters publish updates when deviation, time, or market triggers are met.
Consumers read the latest onchain value.

Advantages:

- simple synchronous read;
- value shared across consumers;
- high availability if updated reliably.

Costs:

- onchain publication expense;
- stale value between updates;
- feeds exist only for supported assets.

### Pull Feed

Signed reports are distributed offchain and submitted with a user transaction
when needed. The contract verifies signature, timestamp, and feed identity.

This reduces continuous publication cost and improves granularity, but consumers
must supply valid data and handle expiry.

### Request-Response

A contract emits a request; oracle nodes perform work and later deliver a
response. The process is asynchronous and needs request identifiers, payment,
timeout, retry, and callback security.

## A Decentralized Price Feed

```mermaid
flowchart LR
    S1["Exchange / source 1"]
    S2["Exchange / source 2"]
    S3["Exchange / source 3"]
    N1["Oracle node 1"]
    N2["Oracle node 2"]
    N3["Oracle node 3"]
    Agg["Offchain and/or onchain aggregation"]
    Feed["Feed contract<br/>value and timestamp"]
    App["Lending / derivatives contract"]
    S1 --> N1
    S2 --> N1
    S2 --> N2
    S3 --> N2
    S1 --> N3
    S3 --> N3
    N1 --> Agg
    N2 --> Agg
    N3 --> Agg
    Agg --> Feed --> App
```

Decentralization has several layers:

- source diversity;
- data-vendor diversity;
- node-operator diversity;
- hosting and geographic diversity;
- aggregation;
- governance and upgrade diversity.

Ten nodes querying one API are not ten independent sources.

## Price Construction

There is no uniquely correct price for every financial purpose. The last trade
can be noisy, a volume-weighted average describes past execution, a mark price
may be designed to prevent unnecessary liquidations, and a redemption price may
come from an issuer. An oracle must choose the measure that matches the contract's
decision and define how it behaves when constituent markets disagree or close.

An oracle must define:

- instrument and venue set;
- quote currency;
- spot, index, mark, or reference price;
- volume and liquidity weighting;
- outlier filtering;
- timestamp and market hours;
- treatment of depegs and venue outages;
- update threshold.

### Median

The median tolerates extreme outliers if fewer than half the inputs are corrupt,
but it does not correct systematic bias or common-source failure.

### Volume-Weighted Price

```text
P_VWAP = Σ_i (P_i × V_i) / Σ_i V_i
```

Reported volume can be manipulated, and historical volume does not guarantee
current executable liquidity.

### Time-Weighted Average Price

```text
P_TWAP = (1 / T) × integral from (t - T) to t of P(u) du
```

Onchain implementations approximate this over observations. TWAP makes a
short manipulation more expensive but responds slowly to genuine price jumps.

## Freshness And Heartbeats

Feeds commonly update when:

- price changes beyond a deviation threshold;
- a maximum heartbeat interval elapses;
- an explicit request is made.

Consumers should validate:

- round or report completeness;
- timestamp;
- maximum age;
- nonzero and plausible range;
- sequencer or chain status where relevant.

A value can be correctly signed and dangerously stale.

## Oracle Manipulation

### Thin-Market Spot Price

An attacker temporarily moves a pool price, uses it to borrow or liquidate, then
reverses the trade. Flash loans make large temporary capital available but are
not the root cause; the root cause is an oracle manipulable within one atomic
transaction.

### Source Compromise

API, exchange, reporter, credential, or network is compromised.

### Collusion

Enough reporters coordinate to submit a false value.

### Governance Attack

Admin changes reporters, thresholds, feed address, or implementation.

### Liveness Failure

Updates stop while consumers continue using old data, or protocols halt and
liquidations accumulate.

### Front-Running

An observer sees an incoming price update and trades before or around it.

## Oracle Risk Controls

- independent sources and operators;
- liquidity-aware source selection;
- median or robust aggregation;
- minimum quorum;
- deviation and heartbeat rules;
- staleness checks in consuming contracts;
- circuit breakers;
- bounded price movement where economically justified;
- multiple feed comparison;
- fallback modes;
- monitoring and alerting;
- cautious governance and timelocks;
- protocol caps and conservative collateral factors.

Fallbacks are not automatically safer. A secondary feed can share the same
sources, be less liquid, or diverge during stress. A pause protects solvency but
can deny legitimate withdrawals.

## Chainlink As A Principal Implementation

Chainlink Data Feeds use decentralized oracle networks to aggregate reports and
publish reference data through onchain aggregator contracts.

At a conceptual level:

1. nodes obtain values from configured data providers;
2. nodes agree offchain under an OCR-family protocol;
3. a compact report with signatures is transmitted onchain;
4. the aggregator verifies and stores it;
5. consumers read through a feed interface or proxy.

Offchain reporting reduces gas relative to every node posting separately while
retaining a quorum-signed report.

### Consumer Checks

Integrations must know:

- chain-specific feed address;
- decimals;
- description and pair direction;
- update policy;
- returned timestamp;
- phase and aggregator changes;
- limitations published for the feed.

### Chainlink Services

The broader architecture includes:

- Data Feeds and data streams;
- Automation for conditional transaction execution;
- VRF for verifiable randomness;
- Proof of Reserve feeds;
- Functions for offchain computation and APIs;
- CCIP for cross-chain messaging.

Each has a distinct trust and failure model; the Chainlink name does not make
them interchangeable.

## Proof Of Reserves

Proof of reserves is an evidence system, not one universal proof.

It may attest:

- an address balance;
- custodian-reported holdings;
- bank or auditor statement;
- liabilities or token supply;
- collateral ratio.

A complete solvency view needs:

```text
net position =
verified assets
- complete liabilities
- senior or encumbering claims
```

An onchain balance proves neither legal ownership nor absence of borrowing,
pledges, undisclosed liabilities, or temporary balance arrangements.

Proof-of-reserve feeds can support circuit breakers but inherit source,
attestation, timing, legal, and oracle risk.

## Automation And Keepers

Contracts cannot wake themselves. An external transaction must call them.
Keepers or automation networks monitor conditions and submit transactions for:

- liquidations;
- periodic rebalancing;
- reward distribution;
- limit orders;
- maintenance.

Risks include:

- no keeper acts because incentives are poor;
- gas spikes make execution uneconomic;
- competing keepers create races;
- condition simulation differs from execution;
- centralized operators censor;
- key or configuration failure.

Automation should be permissionless where feasible, economically incentivized,
and monitored.

## Randomness Oracles

Block variables can be biased by producers. A verifiable random function
returns random-looking output plus proof tied to a secret key and input.

Oracle-based randomness still depends on:

- key holder or threshold availability;
- request confirmation policy;
- callback gas;
- subscription funding;
- correct consumer logic.

Commit-reveal avoids one external provider but can suffer last-revealer bias and
non-participation.

## Indexers

Blockchain storage is optimized for validation, not analytics. Asking for "all
trades by this account grouped by protocol and day" requires:

1. reading blocks, transactions, receipts, logs, and traces;
2. decoding ABIs and protocol semantics;
3. handling reorganizations;
4. writing structured records;
5. aggregating and serving queries.

```mermaid
flowchart LR
    Node["Blockchain node / RPC"]
    Extract["Extract blocks, logs, traces"]
    Decode["Decode contracts and semantics"]
    Store["Database and derived entities"]
    Query["SQL / GraphQL / API"]
    App["Application, dashboard, analytics"]
    Node --> Extract --> Decode --> Store --> Query --> App
```

An indexer is normally offchain. Its database is not consensus state.

## Explorers

Block explorers combine node data, indexing, ABI decoding, address labels,
token metadata, and user interfaces. They are invaluable but can be wrong about:

- contract name;
- token metadata;
- method decoding;
- address attribution;
- internal traces;
- current canonical chain during reorgs.

Verification should use transaction hashes, receipts, bytecode, proofs, and
multiple sources for critical decisions.

## RPC Providers

RPC exposes node methods for:

- current state;
- transaction submission;
- logs;
- simulation;
- historical queries;
- traces where supported.

Provider differences include:

- node client and version;
- archive retention;
- rate limits;
- geographic infrastructure;
- mempool view;
- tracing methods;
- supported chains;
- data caching.

Using two brands on the same cloud or upstream node may not provide meaningful
diversity.

## The Graph

A subgraph defines:

- blockchain and contracts to index;
- starting blocks;
- event or call handlers;
- GraphQL schema;
- deterministic mappings from chain data to entities.

Graph Node reads an RPC endpoint, processes the mapping, stores entities
commonly in PostgreSQL, and serves GraphQL. In The Graph Network, indexers stake
and provide indexing/query service, with protocol incentives and curation.

Subgraphs are reproducible transformations, but errors in:

- source contract address;
- ABI;
- mapping logic;
- start block;
- reorg handling;
- RPC data;

can produce incorrect views.

## Dune And SQL Analytics

SQL analytics platforms ingest raw and decoded blockchain data into queryable
tables. Analysts build transformations, dashboards, and metrics.

Strengths:

- rapid exploratory analysis;
- reproducible SQL;
- shared dashboards;
- cross-chain data.

Limitations:

- ingestion and decoding delay;
- schema changes;
- query mistakes;
- labels and prices with external assumptions;
- dashboard metrics lacking standardized methodology.

A chart is not primary evidence unless its query, tables, time range, and
methodology are reviewed.

## Onchain Versus Offchain Truth

| Data | Authority |
|---|---|
| Contract storage at finalized block | Chain consensus plus proof |
| Decoded event table | Indexer transformation |
| Token name or website | Metadata source |
| Address owner | Attribution evidence |
| USD value | Price source and timestamp |
| Reserve status | Custodian, auditor, bank, or oracle evidence |
| Legal status | Relevant authority and law |

Applications should preserve provenance rather than flattening every value into
one database column.

## Reorganizations

Indexers need a reversible pipeline:

1. ingest block as provisional;
2. associate records with block hash and number;
3. detect parent mismatch;
4. remove or mark orphaned derived data;
5. apply canonical branch;
6. finalize after chain-specific policy.

Offchain actions triggered before finality need idempotency and compensation.

## Data Quality

Quality dimensions include:

- completeness;
- accuracy;
- consistency;
- timeliness;
- lineage;
- uniqueness;
- validity;
- reproducibility.

Derived metrics require explicit definitions. "Protocol revenue" might mean
gross fees, fees retained by contracts, distributions to token holders, or
accounting revenue of a company.

## Trust-Minimized Queries

Possible assurance mechanisms include:

- Merkle storage proofs;
- receipt proofs;
- light-client verification;
- multiple independent indexers;
- signed query responses;
- verifiable computation;
- re-execution.

Proofs increase assurance only if the verifier trusts the block root and the
query statement correctly represents the intended question.

## Analytical Checklist

For an oracle:

1. What exact fact is reported?
2. Which sources measure it?
3. How independent are sources and operators?
4. How are values aggregated?
5. What timestamps, heartbeats, and deviation rules apply?
6. What can governance change?
7. How does the consumer detect stale or implausible data?
8. What happens under manipulation or outage?

For an indexer:

1. Which chain data, node methods, and finality policy are used?
2. How are contracts decoded?
3. How are reorgs reversed?
4. Which derived definitions and external datasets apply?
5. Can results be reproduced?
6. Which claims can be verified with proofs?
7. What availability and provider concentration exist?

## Connections

- [Smart Contracts, Virtual Machines, And Token Standards](smart-contracts-virtual-machines-and-token-standards.md)
  explains why deterministic contracts need external inputs.
- [Blockchain Analytics](../../07-compliance-analytics-regulation-and-security/01-aml-and-blockchain-analytics/blockchain-analytics.md)
  develops attribution and transaction-graph pipelines.
- [DeFi Risk, Security, And Economic Attacks](../../04-decentralized-finance/04-defi-risk-and-failures/defi-risk-security-and-economic-attacks.md)
  covers oracle exploitation and dependency risk.
- [Blockchain Interoperability And Bridges](../../06-interoperability-privacy-and-enterprise-dlt/01-interoperability/blockchain-interoperability-and-bridges.md)
  treats cross-chain messages as external state claims.

## References

- Ethereum.org,
  [Oracles](https://ethereum.org/developers/docs/oracles/)
- Chainlink,
  [Data Feeds documentation](https://docs.chain.link/data-feeds)
- Chainlink,
  [Offchain Reporting](https://docs.chain.link/architecture-overview/off-chain-reporting)
- Chainlink,
  [Proof of Reserve](https://docs.chain.link/data-feeds/proof-of-reserve)
- Chainlink,
  [Automation](https://docs.chain.link/chainlink-automation)
- Chainlink,
  [VRF](https://docs.chain.link/vrf)
- The Graph,
  [Subgraphs](https://thegraph.com/docs/en/subgraphs/overview/)
- The Graph,
  [Indexing overview](https://thegraph.com/docs/en/indexing/overview/)
- Dune,
  [Documentation](https://docs.dune.com/)
- Ethereum.org,
  [JSON-RPC API](https://ethereum.org/developers/apis/json-rpc/)
