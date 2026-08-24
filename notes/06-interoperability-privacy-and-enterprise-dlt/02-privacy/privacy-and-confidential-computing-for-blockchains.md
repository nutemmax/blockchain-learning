---
title: "Privacy and Confidential Computing for Blockchains"
canonical_id: privacy-and-confidential-computing-for-blockchains
node_type: concept
tags:
  - interoperability-privacy-and-enterprise-dlt
  - privacy
source_files:
  - notes/06-interoperability-privacy-and-enterprise-dlt/02-privacy/privacy-and-confidential-computing-for-blockchains.md
prerequisites:
  - cryptography-and-blockchain-data-structures
status: draft
---
# Privacy and Confidential Computing for Blockchains

## Scope

Public blockchains make state and transaction history widely observable so
independent participants can verify consensus. Financial and commercial systems,
however, require confidentiality of identities, balances, positions, prices,
business logic, and negotiations. Privacy technology tries to preserve necessary
verification while revealing less data.

No single technique provides "privacy." A system must define:

- what data is hidden;
- from whom;
- at what time;
- what statements remain verifiable;
- who can authorize disclosure;
- what metadata leaks;
- what trust and key-management assumptions remain; and
- how errors, law, and governance are handled.

This note explains pseudonymity, encryption, commitments, zero-knowledge proofs,
multi-party computation, trusted execution environments, fully homomorphic
encryption, privacy groups, selective disclosure, confidential tokens, and
compliance-aware privacy.

## 1. Privacy Properties

### 1.1 Confidentiality

Unauthorized parties cannot learn protected content. Examples include transfer
amount, account balance, contract terms, or identity attributes.

### 1.2 Anonymity

An observer cannot identify the real-world person or organization taking an
action.

### 1.3 Unlinkability

An observer cannot determine that two actions, addresses, or records belong to
the same entity.

### 1.4 Unobservability

An observer cannot determine that an action occurred at all. This is much harder
on a public ledger because transaction timing and gas use are visible even if
payloads are encrypted.

### 1.5 Selective disclosure

An authorized party can reveal a specific fact or record without revealing
everything else.

### 1.6 Auditability

The system can demonstrate that transactions and controls were valid, perhaps to
an auditor or regulator, without public disclosure.

These properties can conflict. A system optimized for public verifiability may
leak metadata; a system optimized for secrecy may make independent audit or
recovery harder.

## 2. Threat Modeling

Privacy is relative to an adversary.

Potential observers include:

- the general public;
- transaction counterparties;
- other consortium members;
- validators and sequencers;
- node, RPC, and wallet providers;
- block builders and searchers;
- network operators;
- cloud and hardware providers;
- application administrators;
- custodians and key managers;
- analytics companies;
- governments, courts, and regulators; and
- attackers who compromise one or several of these.

Data states also differ:

- **at rest:** stored in databases, nodes, wallets, and backups;
- **in transit:** moving through networks and APIs;
- **in use:** processed by a program;
- **onchain:** permanently replicated or committed;
- **offchain:** held by parties, proving services, or confidential compute; and
- **after disclosure:** once plaintext is released, cryptography cannot make
  recipients forget it.

A privacy claim is meaningful only if it names adversary and data state.

## 3. Pseudonymity Is Not Anonymity

Public chains use addresses rather than legal names, but their transaction graphs
are persistent. Identity can be inferred through:

- exchange or custodian records;
- address reuse;
- transfers among known entities;
- timing and amount correlation;
- gas-funding patterns;
- IP and RPC metadata;
- smart-contract interactions;
- public naming services;
- counterparties; and
- offchain leaks.

Once an address cluster is attributed, historical transactions can be analyzed
retroactively. Generating a new address helps only if funding and behavior do not
link it back.

Encryption of payload fields also leaves metadata: sender, contract, time, gas,
frequency, and sometimes ciphertext size. Traffic analysis can reveal business
relationships without decrypting content.

## 4. Basic Encryption and Hashing

### 4.1 Encryption

Encryption transforms plaintext into ciphertext under a key.

- **symmetric encryption** uses the same secret for encryption and decryption;
- **public-key encryption** lets anyone encrypt to a recipient's public key while
  only the private-key holder decrypts; and
- **hybrid encryption** encrypts data with a symmetric key and encrypts that key
  for authorized recipients.

Ordinary encryption protects storage and communication but does not let a public
smart contract compute over secret values. A validator must either see plaintext
or verify another mechanism.

### 4.2 Hashes

A cryptographic hash is a one-way digest, not encryption. Hashing a low-entropy
value such as a yes/no answer or small salary range does not hide it: an attacker
can hash every possible value.

### 4.3 Commitments

A commitment lets a party bind to a value while hiding it. A simplified
construction combines the value with unpredictable randomness:

```text
commitment = hash(value || random secret)
```

Later, revealing both value and randomness opens the commitment. A good
commitment is:

- hiding: the commitment does not reveal the value; and
- binding: the creator cannot open it as a different value.

Commitments support sealed bids, hidden balances, and zero-knowledge protocols.

## 5. Zero-Knowledge Proofs

A zero-knowledge proof lets a prover convince a verifier that a statement is true
without revealing the underlying witness.

Examples:

- a transfer conserves value without revealing amounts;
- a user is over 18 without revealing a birth date;
- a wallet is on an approved list without revealing which entry;
- a computation followed specified rules;
- liabilities do not exceed committed assets; or
- a source-chain event finalized without replaying the entire chain.

### 5.1 Three core properties

- **completeness:** an honest prover with a valid witness can convince the
  verifier;
- **soundness:** a false statement should not be accepted except with negligible
  probability; and
- **zero knowledge:** the proof reveals no information beyond the truth of the
  statement under the formal model.

### 5.2 Circuits and public inputs

The computation is represented as constraints. Private witness values remain
secret; public inputs and outputs are visible. The verifier checks a succinct
proof against a verification key.

Privacy depends on circuit design. A proof can be cryptographically zero
knowledge while public inputs, timing, or application behavior reveal the user.

### 5.3 SNARKs and STARKs

Succinct non-interactive arguments of knowledge, or SNARKs, can provide small
proofs and fast verification. Some systems require a trusted setup; universal or
transparent constructions reduce or remove ceremony-specific trust.

Scalable transparent arguments of knowledge, or STARKs, use hash-based
commitments, avoid trusted setup, and have different proof-size and performance
trade-offs.

Neither label guarantees secure implementation. Analyze the proof system,
cryptographic assumptions, circuit, compiler, setup, verifier, and parameters.

### 5.4 Confidential tokens

A UTXO-style confidential token can store commitments to notes. A transfer proof
shows:

- input notes exist and belong to the spender;
- they have not previously been spent;
- output amounts are in range;
- inputs equal outputs plus any fee; and
- policy conditions hold.

Nullifiers reveal that a note has been spent without revealing which committed
note it was, provided the anonymity set and implementation are sound.

### 5.5 Limitations

Zero-knowledge proofs move trust from revealing the witness to verifying a
statement encoded in a circuit. They do not guarantee that the statement captures
the intended financial rule or that offchain inputs are true. Circuit design,
proving software, setup assumptions, and application integration become the new
assurance surface.

- proof generation can be computationally expensive;
- circuits are specialized and difficult to audit;
- bugs can permit hidden inflation;
- trusted setup may be compromised;
- data availability remains necessary;
- private state coordination is complex;
- anonymity sets can be small; and
- selective disclosure and recovery require additional design.

## 6. Multi-Party Computation

Secure multi-party computation, or MPC, lets several parties compute a function
over private inputs without revealing those inputs to one another beyond the
agreed output.

### 6.1 Threshold signatures

The most common blockchain use is threshold signing. A private key is divided
among parties so that a threshold must cooperate to sign. No single machine
holds the complete key.

Threshold signing protects custody but does not make onchain transaction data
private.

### 6.2 General MPC

Parties can jointly calculate auctions, risk metrics, matching, or compliance
results. Protocols use secret sharing, garbled circuits, or other techniques.

Trade-offs include:

- multiple interactive rounds;
- network latency;
- participant availability;
- honest-majority or dishonest-majority assumptions;
- preprocessing;
- complex implementation; and
- output leakage.

MPC distributes trust; it does not remove it. Security depends on how many
participants may collude and whether malicious behavior is detectable.

## 7. Trusted Execution Environments

A trusted execution environment, or TEE, is a hardware-isolated region that
executes code and protects its memory from the host system. Remote attestation
can provide evidence that specified code runs in specified hardware.

Blockchains use TEEs for:

- confidential contract execution;
- private order flow;
- oracle computation;
- key custody;
- randomness;
- proof acceleration; and
- bridge validation.

### 7.1 Strengths

- supports general programs;
- often faster than advanced cryptography;
- can protect data while in use; and
- integrates with conventional applications.

### 7.2 Risks

- dependence on hardware manufacturer and attestation roots;
- side-channel and speculative-execution attacks;
- firmware and microcode vulnerabilities;
- rollback and state-continuity problems;
- physical attacks;
- attestation-service outages;
- opaque proprietary components; and
- difficulty proving that inputs and outputs reflect the intended external
  world.

A TEE changes trust from a software operator to a hardware and attestation
supply chain. Defense in depth may combine TEEs with replication, MPC, and
cryptographic proofs.

## 8. Fully Homomorphic Encryption

Fully homomorphic encryption, or FHE, permits computations on ciphertexts such
that decryption of the result matches computation on plaintexts.

```text
decrypt(evaluate(encrypt(x), function)) = function(x)
```

The evaluator can process protected values without learning them.

### 8.1 Why it matters

FHE can support confidential state that remains composable:

- encrypted balances;
- private bids;
- hidden votes;
- confidential credit rules;
- private risk calculations;
- sealed trading strategies; and
- encrypted identity attributes.

Unlike a ZK proof, which proves that a particular computation was performed,
FHE allows a designated evaluator to perform new computations on encrypted data.
The techniques can be combined.

### 8.2 Keys

An FHE system commonly has:

- a public encryption key;
- a secret decryption key; and
- evaluation keys that support homomorphic operations.

The secret key is a high-value trust root. Threshold MPC can distribute it among
several key-management operators.

### 8.3 Noise and bootstrapping

Homomorphic operations increase noise in ciphertext. Bootstrapping refreshes a
ciphertext so further computation remains possible. Modern schemes have made
this practical for selected workloads, but computation and ciphertexts remain
far more expensive than plaintext operations.

### 8.4 Limits

- high computation and storage overhead;
- limited or specialized data types;
- difficult debugging;
- key-management and decryption governance;
- leakage from access patterns and public control flow;
- offchain coprocessor availability;
- cryptographic parameter risk; and
- need to prove that external inputs are well formed.

FHE hides values, not necessarily who transacts, which contract executes, or how
often.

## 9. Privacy Groups and Private Ledgers

A permissioned blockchain can restrict transaction payloads to a subset of
members while anchoring proofs or hashes in shared consensus.

Common patterns:

- private transaction managers distribute payloads only to group members;
- group members execute a private state machine;
- the public or consortium ledger records an opaque marker or commitment;
- notaries or validators order and finalize shared events; and
- authorized parties retain private state and audit data.

This can be efficient for enterprise workflows, but:

- group members see plaintext;
- membership and identity services are trusted;
- data availability depends on participants;
- cross-group atomicity is hard;
- metadata may leak; and
- shared public verification is weaker than a ZK proof of correct execution.

## 10. Selective Disclosure and Digital Credentials

A verifiable credential is a signed set of claims from an issuer. A holder can
present it to a verifier. Privacy-preserving credential systems may reveal only
selected attributes or prove predicates.

Examples:

- prove residency in an allowed jurisdiction without revealing address;
- prove investor qualification without revealing income;
- prove membership in a screened set without revealing a public identity;
- prove a credential has not expired or been revoked.

### 10.1 Design components

- issuer identity and trust framework;
- holder binding;
- signature or proof scheme;
- schema and semantics;
- revocation or status;
- selective disclosure;
- verifier policy;
- replay prevention; and
- data minimization.

Publishing a stable credential identifier onchain can create correlation even if
claims are hidden. Pairwise identifiers and unlinkable presentations may help.

## 11. Privacy Pools and Compliance-Aware Anonymity

Pool-based systems break direct links between deposits and withdrawals by
creating an anonymity set. A user proves ownership of an unspent note without
revealing which deposit created it.

Compliance-aware variants can let users prove that their funds belong to an
approved association set or do not derive from a designated exclusion set.

This creates nuanced possibilities:

- users keep transaction history private from the public;
- regulated counterparties request proof of policy compliance;
- illicit deposits can be excluded from a user's claimed set; and
- disclosure can be selective rather than universal.

Challenges remain:

- who defines the sets;
- false positives and appeals;
- set-update timing;
- small anonymity sets;
- frontend and network metadata;
- sanctions and legal treatment;
- proof complexity; and
- coercive or excessive disclosure.

Privacy and compliance are not logically incompatible, but both require explicit
governance.

## 12. Confidentiality for Financial Assets

A confidential financial asset must hide commercially sensitive information
while preserving the controls that make the asset legally and financially valid.
For example, a bond transfer may conceal price and position size from the public
but still need to prove investor eligibility, prevent double spending, update the
authoritative register, and reveal records to authorized supervisors or courts.
Privacy is therefore selective information governance, not universal secrecy.

A confidential token may need to hide:

- holder identity;
- balance;
- transfer amount;
- price;
- asset type;
- settlement instructions; and
- business purpose.

It may still need to prove:

- issuer authorization;
- conservation of supply;
- no double spend;
- holder eligibility;
- position or concentration limits;
- sanctions policy;
- sufficient collateral;
- DvP or PvP atomicity; and
- auditable issuer supply.

### 12.1 Confidential stablecoin

Encrypted transfers do not solve backing or redemption. The issuer still holds
reserve assets and exercises freeze, mint, burn, and disclosure powers.

### 12.2 Confidential securities

Securities require ownership records, transfer restrictions, corporate actions,
tax, and legal orders. A private transfer protocol must remain synchronized with
the legally recognized register.

### 12.3 Private DeFi

Confidential balances and orders reduce information leakage and front-running,
but protocols need private liquidation, oracle, solvency, and risk logic.
Hidden leverage can make system-wide risk harder to monitor. Selective aggregate
proofs may be needed.

## 13. Metadata and Side Channels

Even strong cryptography can leak through:

- transaction time and frequency;
- sender gas funding;
- public contract and function selector;
- ciphertext or proof size;
- access-control updates;
- decryption requests;
- network IP;
- wallet telemetry;
- browser fingerprints;
- error messages;
- latency;
- amount rounding; and
- correlation with offchain events.

Mitigations include batching, relayers, cover traffic, private transaction
submission, standardized sizes, account abstraction, network anonymity, delayed
release, and careful logging. Every mitigation has cost and usability trade-offs.

## 14. Key Management and Disclosure Governance

Privacy systems often concentrate power in decryption keys.

Questions include:

- Is there one global secret or per-user keys?
- Is the key distributed by threshold MPC?
- How many parties must cooperate?
- Who selects and removes key holders?
- Can they decrypt any record or only authorized ciphertexts?
- Is decryption logged and publicly auditable?
- How are court orders handled?
- Can users recover after key loss?
- What happens if key shares are destroyed?
- Is historical ciphertext safe if the key is later compromised?

Forward secrecy, key rotation, purpose-limited decryption, and hardware security
can reduce risk. No governance slogan substitutes for a full key lifecycle.

## 15. Choosing a Technique

| Requirement | Typical technique | Main trade-off |
|---|---|---|
| Prove a fact without revealing inputs | Zero-knowledge proof | Circuit and proving complexity |
| Compute jointly across organizations | MPC | Interaction and participant availability |
| General confidential computation | TEE | Hardware and attestation trust |
| Compute on persistent encrypted state | FHE | Performance and key governance |
| Hide data from non-group members | Privacy group | Group members see plaintext |
| Bind now, reveal later | Commitment | Requires later opening or proof |
| Prove identity attributes selectively | Privacy-preserving credentials | Issuer and revocation framework |
| Protect wallet authority | Threshold signature or MPC custody | Does not hide onchain data |

Hybrid designs are common:

- ZK proofs validate encrypted inputs;
- FHE computes on them;
- threshold MPC controls decryption;
- a TEE accelerates proving;
- a public chain orders commitments; and
- credentials prove eligibility.

The hybrid system inherits every critical dependency.

## 16. Evaluation Checklist

1. data and metadata being protected;
2. adversaries and collusion threshold;
3. public statements and leakage;
4. cryptographic construction and assumptions;
5. trusted setup or hardware roots;
6. keys, custody, rotation, and recovery;
7. who can decrypt and under what governance;
8. computation, proof, and verification cost;
9. state and data availability;
10. identity, access control, and revocation;
11. audit and selective disclosure;
12. interoperability with public and private state;
13. upgrade and emergency powers;
14. handling of erroneous or malicious ciphertext;
15. side-channel and metadata protections;
16. legal retention, erasure, and disclosure obligations;
17. open-source status, audits, and maturity; and
18. degradation when a service is unavailable.

## 17. Key Takeaways

1. Blockchain addresses are pseudonyms, not durable anonymity.
2. Privacy has several dimensions: confidentiality, anonymity, unlinkability,
   unobservability, selective disclosure, and auditability.
3. Hashing low-entropy data does not make it secret.
4. ZK proves statements about hidden witnesses; MPC computes across secret inputs;
   TEEs protect execution in hardware; FHE computes on ciphertext.
5. Each technique moves rather than eliminates trust, cost, or governance.
6. Metadata can defeat otherwise strong content confidentiality.
7. Confidential financial assets still need enforceable ownership, supply
   integrity, settlement, servicing, and regulation.
8. Decryption-key governance is often the most important system-level risk.
9. Privacy and compliance can coexist through selective disclosure and
   policy proofs, but governance determines whose policy is enforced.
10. A meaningful privacy claim always states what is hidden, from whom, and under
    which assumptions.

## Related Notes

- [Cryptography and Blockchain Data Structures](../../02-blockchain-foundations/01-core-architecture/cryptography-and-blockchain-data-structures.md)
- [Zama](zama.md)
- [Paladin](paladin.md)
- [Wallets, Key Management, and Digital-Asset Custody](../../03-digital-assets-and-market-structure/04-wallets-and-custody/wallets-key-management-and-digital-asset-custody.md)
- [Blockchain Analytics](../../07-compliance-analytics-regulation-and-security/01-aml-and-blockchain-analytics/blockchain-analytics.md)

## References

- NIST, [Privacy Framework](https://www.nist.gov/privacy-framework)
- NIST, [Privacy-Enhancing Cryptography project](https://csrc.nist.gov/projects/pec)
- NIST, [Multi-Party Threshold Cryptography](https://csrc.nist.gov/projects/threshold-cryptography)
- HomomorphicEncryption.org, [Homomorphic Encryption Standard](https://homomorphicencryption.org/standard/)
- IACR Cryptology ePrint Archive, [Publications](https://eprint.iacr.org/)
- Ethereum, [Zero-knowledge proofs](https://ethereum.org/en/zero-knowledge-proofs/)
- Zcash, [Protocol specification](https://zips.z.cash/protocol/protocol.pdf)
- Electric Coin Company, [Halo](https://electriccoin.co/blog/explaining-halo-2/)
- Confidential Computing Consortium, [Confidential Computing](https://confidentialcomputing.io/about/)
- W3C, [Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model-2.0/)
- W3C, [Data Integrity BBS Cryptosuites](https://www.w3.org/TR/vc-di-bbs/)
- Ethereum Improvement Proposal 5564, [Stealth Addresses](https://eips.ethereum.org/EIPS/eip-5564)
- Ethereum Improvement Proposal 7503, [Zero-Knowledge Wormholes](https://eips.ethereum.org/EIPS/eip-7503)
- Privacy Pools, [Technical paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4563364)
- Bank for International Settlements, [Privacy in digital payments](https://www.bis.org/publ/othp37.htm)
