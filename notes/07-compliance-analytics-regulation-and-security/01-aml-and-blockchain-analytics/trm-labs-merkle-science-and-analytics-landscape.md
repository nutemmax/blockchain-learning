# TRM Labs, Merkle Science, and the Blockchain-Analytics Landscape

## Scope

Blockchain-intelligence vendors transform public ledger data and external
evidence into address attributions, entity clusters, risk signals, transaction
monitoring, and investigation tools. Their most valuable data is not the raw
blockchain, which can often be obtained independently, but the proprietary link
between onchain activity and real-world actors.

This note studies TRM Labs and Merkle Science and places them beside Chainalysis,
Elliptic, and other providers. It explains how to compare coverage, attribution,
exposure models, investigations, APIs, model governance, and evidentiary quality.
It is not a vendor ranking.

Product coverage and figures change frequently. Specific descriptions are
current to July 2026 and should be verified against contract scope and a live
test.

## 1. The Product Categories

### 1.1 Wallet screening

Given an address, screening returns:

- direct attribution;
- entity or service category;
- sanctions designation;
- risk categories;
- direct and indirect exposure;
- behavioral signals;
- chain and asset context;
- confidence and evidence; and
- a configurable risk decision.

Screening may occur before allowing a withdrawal, accepting a deposit address,
onboarding a counterparty, or interacting with a smart contract.

### 1.2 Transaction monitoring

Monitoring evaluates deposits, withdrawals, transfers, and customer behavior
over time. It creates alerts for rules such as:

- sanctioned counterparty;
- darknet, scam, ransomware, theft, or terrorist-financing exposure;
- mixer or privacy-service interaction;
- rapid pass-through;
- peel chain;
- chain hopping;
- structuring below limits;
- high-risk jurisdiction or exchange;
- unusual volume or velocity; and
- behavioral change.

The vendor signal is one input to a regulated institution's monitoring system.
It does not replace customer risk, expected activity, source of funds, fiat
transactions, device data, or analyst judgment.

### 1.3 Investigations

Investigation products visualize and trace flows, label services, follow swaps
and bridges, record analyst reasoning, and export case evidence.

They need:

- transaction-level provenance;
- clustering with confidence;
- cross-chain continuity;
- token and smart-contract decoding;
- time and value accounting;
- collaboration and case notes;
- reproducible output; and
- preservation of vendor data as it existed at the decision date.

### 1.4 Data platform and APIs

Institutions may consume:

- address and entity APIs;
- transaction risk APIs;
- sanctions feeds;
- raw normalized ledger data;
- attribution and cluster feeds;
- event webhooks;
- graph query interfaces;
- case-management integrations; and
- cloud data shares.

API scope can differ from the user interface. Contract terms should specify
chains, data freshness, rate limits, historical access, and redistribution.

## 2. TRM Labs

### 2.1 Platform

TRM offers an integrated blockchain-intelligence platform whose main functions
include:

- Wallet Screening;
- Transaction Monitoring;
- Forensics;
- Know-Your-VASP and entity risk;
- sanctions and threat intelligence;
- case workflow and reporting;
- data APIs; and
- training and investigative services.

TRM markets to crypto businesses, financial institutions, government,
law-enforcement, and national-security users.

### 2.2 Data and attribution

TRM combines:

- direct attribution and customer intelligence;
- public and commercial sources;
- sanctions and government designations;
- open-source and dark-web research;
- address clustering;
- transaction and smart-contract decoding;
- behavioral models; and
- analyst validation.

The product exposes source and confidence information for attributions according
to official materials. Users should test how detailed this evidence is for their
licensed dataset.

### 2.3 Coverage tiers

TRM distinguishes levels of chain support. Its July 2026 company materials
reported screening across more than 184 blockchains, with fuller real-time
indexing, tracing, and compliance functionality on a smaller subset.

This illustrates why headline chain counts are misleading. Coverage may mean:

- only direct sanctioned-address lookup;
- native-asset transaction parsing;
- full token and smart-contract decoding;
- entity clustering;
- indirect exposure;
- cross-chain tracing; or
- complete monitoring and forensics.

Each required chain and asset should be mapped to exact functionality.

### 2.4 Forensics and cross-chain tracing

TRM Forensics provides graph-based tracing across supported chains. Relevant
features include:

- entities and addresses;
- automatic tracing;
- cross-chain swaps and bridges;
- transaction paths;
- exposure to services;
- annotations and collaboration;
- reporting; and
- integration with operational intelligence.

Cross-chain traces can be:

- deterministic, when an issuer burn-and-mint ID links both legs;
- attributed, when a bridge event exposes mappings;
- heuristic, when amounts and timing correlate;
- intelligence-based, when a custodial swap service supplies or reveals data; or
- unresolved.

The interface should distinguish these confidence levels.

### 2.5 Network collaboration

TRM has supported collaborative networks through which investigators,
stablecoin issuers, exchanges, and other services can share verified alerts and
interdict illicit funds. Such networks can shorten the time between theft and
freeze.

They introduce governance questions:

- who may submit a flag;
- evidence threshold;
- review and appeal;
- data accuracy;
- confidentiality;
- legal authority to freeze;
- jurisdiction;
- liability for a false flag; and
- expiration of intelligence.

### 2.6 TRM analytical strengths and limits

TRM should be evaluated as a layered data and workflow system, not by one
headline chain count. A chain can be technically ingested without having mature
entity attribution, decoded DeFi activity, cross-chain tracing, or low-latency
monitoring. The relevant strength is the depth available for the institution's
actual assets and typologies, with evidence that analysts can explain.

Potential strengths to test:

- broad multi-chain and cross-chain coverage;
- rapid addition of emerging networks;
- configurable screening and monitoring;
- integrated investigations;
- source and confidence transparency;
- threat-intelligence and public-sector experience; and
- APIs and real-time signals.

Limits to evaluate:

- feature depth varies by chain tier;
- company-reported accuracy needs independent test data;
- predictive or behavioral labels may be harder to explain than direct
  attribution;
- SaaS dependence and data residency;
- evolving product taxonomy; and
- false-positive cost at high transaction volume.

## 3. Merkle Science

### 3.1 Platform

Merkle Science describes its offering as a predictive crypto risk and
intelligence platform. Its main products include:

- **Compass:** wallet screening, transaction monitoring, rules, alerts, and case
  workflows;
- **Tracker:** investigations and fund-flow tracing;
- **Data Platform:** queries, datasets, and analytics; and
- **Onchain Pulse:** ecosystem and token risk monitoring.

The company emphasizes behavioral detection alongside known-address attribution.

### 3.2 Compass

Compass is designed for:

- pre-transaction wallet screening;
- ongoing transaction monitoring;
- customer-level risk views;
- direct and indirect exposure;
- configurable policy and risk categories;
- behavioral rules;
- sanctions monitoring;
- case notes, audit trails, and reports; and
- API integration.

Behavioral monitoring can identify activity before an address is definitively
attributed, but it should create a reviewable signal rather than an unsupported
claim of ownership.

### 3.3 Tracker

Tracker provides graph investigations across supported chains, tokens, bridges,
and smart-contract activity. Official materials describe:

- address and cluster analysis;
- DeFi and smart-contract decoding;
- cross-chain visualization;
- automatic expansion of related flows;
- wallet monitoring and alerts;
- case collaboration;
- custom tags and offchain evidence; and
- evidence and attribution sources.

The quality of a forensic graph depends on the transformation behind every edge.
An ERC-20 transfer event, internal value call, DEX swap, bridge mint, or exchange
deposit must not be represented as if each were the same kind of direct payment.

### 3.4 Predictive and behavioral risk

Merkle Science emphasizes going beyond static blacklists. Behavioral features
may include:

- transaction velocity;
- exposure patterns;
- service usage;
- fan-in and fan-out;
- mixer-like behavior;
- rapid cross-chain movement;
- address age;
- interactions with newly risky infrastructure; and
- patterns learned from known cases.

Advantages:

- earlier warning for unknown addresses;
- detection of typologies rather than only named actors; and
- adaptable rules for changing threats.

Risks:

- opaque feature weights;
- circularity if vendor labels train vendor models;
- bias toward known enforcement cases;
- false positives for legitimate DeFi behavior;
- model drift;
- lack of stable explanations; and
- confusion between suspicion and attribution.

Model output should be labeled as behavioral risk with confidence, not converted
into a factual entity name.

### 3.5 Merkle Science strengths and limits

Merkle Science's emphasis on predictive and behavioral signals can be valuable
where illicit infrastructure changes faster than confirmed attribution. That
same advantage creates a validation obligation: a model may rank a novel pattern
as risky without proving who controls the wallet or why every similar pattern is
illicit. Production testing should therefore measure investigative value and
false-positive burden separately from marketing measures of detection.

Potential strengths to test:

- configurable behavioral rules;
- integrated monitoring and investigations;
- cross-chain and DeFi focus;
- evidence-backed attribution;
- customer-level aggregation;
- flexible workflows; and
- ecosystem risk analysis.

Limits to evaluate:

- depth and freshness vary by chain and asset;
- predictive claims require rigorous validation;
- smaller customer intelligence network may affect some attributions;
- public specifications are limited for proprietary methods; and
- product maturity must be tested under production volumes.

## 4. Chainalysis and Elliptic in Context

Dedicated notes cover
[Chainalysis and Elliptic](chainalysis-and-elliptic.md). At a high level:

### Chainalysis

Major product families include:

- KYT for transaction monitoring;
- Reactor and related investigation tools;
- wallet and entity screening;
- data feeds and APIs;
- government and incident-response services; and
- protocol-security capabilities added through acquisitions.

The company emphasizes a large attribution network, clustering, government and
exchange adoption, and court-tested methodology. Company metrics should still be
validated and scoped to exact use.

### Elliptic

Elliptic offers wallet and transaction screening, cross-chain analytics,
investigations, holistic multi-asset wallet views, VASP intelligence, and data
services. Its Holistic Screening approach is designed to follow risk across
assets and chains.

### Important comparison point

Feature labels conceal methodological differences. Two vendors can both claim
“cross-chain tracing” while one links only canonical burn-and-mint events and the
other also infers swaps through exchanges or solvers. A comparison should use the
same known transactions and ask each product to expose its evidence, confidence,
and unsupported gaps.

All leading vendors combine public data, heuristics, and proprietary
intelligence. Differentiation tends to come from:

- attribution breadth and confidence;
- chain and protocol parsing;
- cross-chain linkage;
- latency;
- investigation workflow;
- API and data access;
- explainability;
- customer-contributed intelligence;
- public-sector and regulated-market support; and
- commercial and deployment model.

## 5. Other Providers and Open Tools

The landscape includes:

- **CipherTrace**, part of Mastercard, offering crypto intelligence and
  compliance capabilities;
- **Scorechain**, providing AML and transaction-monitoring tools;
- **Coinfirm**, offering AML risk and analytics;
- **Crystal**, offering investigations and compliance;
- **Blocktrace**, **Breadcrumbs**, and specialized investigation products;
- **GraphSense**, an open-source analytics platform;
- **BlockSci**, an academic analytics framework for supported UTXO chains;
- chain-specific explorers and indexers; and
- internal data-engineering and intelligence teams.

Open tools improve reproducibility and reduce dependence but generally lack the
same proprietary attribution feeds. A hybrid model can preserve raw evidence and
independent calculations while licensing vendor intelligence.

## 6. How Attribution Is Built

### 6.1 Ground-truth evidence

Attribution is strongest when evidence connects an address to control, not merely
to similar behavior. A test deposit to an exchange can identify a service deposit
address; a signed message can prove that a party controlled a key at a point in
time. Even ground truth has scope: control can change, a hosted address may belong
to the service rather than its customer, and evidence can become stale.

High-confidence attribution may come from:

- a service publishing its address;
- a deposit or withdrawal controlled during testing;
- legal process or law-enforcement evidence;
- customer-provided address ownership;
- a seized wallet;
- signed proof of control;
- source code or contract ownership; or
- reliable public records.

### 6.2 Clustering

Heuristics group addresses likely controlled by one entity.

Bitcoin examples:

- common-input ownership;
- change-address detection;
- sweep behavior;
- wallet fingerprinting; and
- deposit-cluster patterns.

Account-based chain examples:

- common funding;
- repeated operational flows;
- ownership and proxy contracts;
- exchange deposit infrastructure;
- gas sponsor;
- multisignature signers; and
- behavioral similarity.

Every heuristic has exceptions. CoinJoin breaks common-input assumptions;
custodial deposit addresses can represent many customers; account abstraction
can make one sponsor fund unrelated users.

### 6.3 Entity classification

An attributed cluster is classified as exchange, mixer, DeFi protocol, scam,
sanctioned entity, miner, merchant, ransomware, and so on. Category and risk are
separate:

- "exchange" describes a service type;
- "unlicensed high-risk exchange" adds risk;
- "sanctioned exchange" adds a legal designation.

### 6.4 Confidence and time

Attribution should include:

- source;
- confidence;
- first and last valid date;
- address role;
- chain;
- analyst review;
- superseded labels; and
- evidence accessible for challenge.

An address can change use or be falsely claimed by another party. Historical
decisions need the label version used at the time.

## 7. Exposure Models

### 7.1 Direct ownership

The address itself is attributed to an entity. This is generally stronger than
transactional exposure.

### 7.2 Direct counterparty

The address sent to or received from a risky entity.

### 7.3 Indirect exposure

Funds passed through intermediaries. Risk can be measured by:

- hop count;
- value proportion;
- time;
- direction;
- path type;
- service category;
- attribution confidence; and
- transaction behavior.

There is no universal correct rule. Treating every historical descendant of a
tainted coin as equally risky produces contamination explosion.

### 7.4 Source-of-funds tracing

Proportional, first-in-first-out, last-in-first-out, poison, and haircut methods
allocate value through merged flows differently. Account-based tokens and DEX
swaps complicate these models.

Vendor interfaces should reveal or document the allocation method used for
alerts.

## 8. Validation and Benchmarking

A defensible test uses cases whose truth is known independently.

### 8.1 Coverage test

Create required chain and asset matrix:

- native transfers;
- major and long-tail tokens;
- internal calls;
- NFTs;
- DEX swaps;
- bridges;
- rollups;
- staking;
- account abstraction;
- privacy protocols; and
- failed or reverted transactions.

### 8.2 Attribution test

Use addresses with documented ground truth. Measure:

- precision;
- recall;
- cluster purity;
- false merges;
- false splits;
- confidence calibration;
- time to new attribution; and
- evidence quality.

### 8.3 Monitoring test

Replay historical transactions and synthetic scenarios. Measure:

- alert precision and recall;
- analyst review time;
- duplicate alerts;
- latency;
- policy flexibility;
- customer aggregation;
- case workflow; and
- reproducibility.

### 8.4 Performance test

Test actual peak rates, not average:

- API latency percentiles;
- batch throughput;
- rate limits;
- webhook delay;
- availability;
- backfill speed;
- export size; and
- degraded mode.

### 8.5 Cross-chain test

Include known:

- canonical bridge transfers;
- issuer burn-and-mint;
- liquidity bridges;
- cross-chain swaps;
- exchange-mediated swaps;
- intent solvers; and
- failed routes.

Record whether linkage is deterministic, attributed, or heuristic.

## 9. Model Governance and Explainability

A risk score should never be the final reason for an adverse decision without
supporting facts.

A controlled program maintains:

- feature and rule definitions;
- versioned models;
- validation before deployment;
- approval for threshold changes;
- false-positive and false-negative monitoring;
- override rationale;
- data lineage;
- change notification;
- periodic recalibration; and
- independent review.

Machine learning can prioritize cases, but high-stakes enforcement requires
traceable evidence. Generative AI summaries should link to transactions,
attributions, and rules and must not invent certainty.

## 10. Data, Security, and Legal Considerations

Public-chain transparency does not make an analytics deployment non-sensitive.
The vendor may receive the private mapping between a customer and a wallet,
internal investigation hypotheses, and data indicating that a report to
authorities is under consideration. Combining that information with public asset
balances can create a much more sensitive dataset than either source alone.

Security review must also follow how shared intelligence is created. Customer
submissions may improve ecosystem attribution, but they need a lawful basis,
quality controls, source protection, and a process for correcting labels. The
contract should make clear whether submitted data stays tenant-specific, enters a
shared graph, or can be disclosed to government users.

Vendor platforms may receive:

- customer wallet addresses;
- transaction IDs;
- internal customer identifiers;
- case notes;
- suspicious-activity narratives;
- law-enforcement requests;
- IP or device data; and
- unpublished threat intelligence.

Assess:

- data residency and subprocessors;
- encryption and tenant separation;
- staff access;
- retention and deletion;
- use of customer data to enrich shared intelligence;
- government access;
- incident response;
- audit reports;
- export on termination;
- API logs;
- evidence preservation; and
- contractual liability.

Blockchain data is public, but the mapping to a named customer is personal and
confidential data.

## 11. Neutral Selection Framework

| Dimension | Questions |
|---|---|
| Required coverage | Does full functionality exist for each chain, token, and protocol? |
| Attribution | What evidence, confidence, history, and challenge process exist? |
| Cross-chain | Are links deterministic, intelligence-based, or heuristic? |
| Monitoring | Can rules reflect customer, product, jurisdiction, direction, and exposure type? |
| Investigations | Can analysts reproduce paths and preserve evidence? |
| Data access | Are raw data, labels, APIs, exports, and historical versions available? |
| Validation | What independent test supports accuracy claims? |
| Workflow | Does it integrate with KYC, case, SAR, and sanctions systems? |
| Operations | What are latency, availability, support, and incident commitments? |
| Governance | How are labels and models changed and audited? |
| Security | How is sensitive customer and case data protected? |
| Commercial | Are pricing, limits, usage rights, and exit practical? |

There may be no single winner. An organization can use one primary monitoring
vendor, another for complex investigations, and independent data for
cross-validation.

## 12. Key Takeaways

1. The proprietary value of analytics vendors is attribution and intelligence,
   not merely public ledger ingestion.
2. TRM combines screening, monitoring, forensics, data, and collaborative threat
   networks with broad but tiered chain coverage.
3. Merkle Science emphasizes behavioral and predictive monitoring through
   Compass and investigation through Tracker.
4. Headline chain counts are incomparable unless the exact feature level is
   stated.
5. Behavioral risk is a model signal, not proof of entity ownership or crime.
6. Cross-chain links may be deterministic, attributed, or heuristic and should
   be labeled accordingly.
7. Exposure depends on allocation method, direction, time, proportion, and path;
   hop count alone is inadequate.
8. Vendor claims should be tested on independently known addresses and complete
   protocol scenarios.
9. Explainability, historical label preservation, and data lineage are essential
   for defensible compliance and court use.
10. A vendor provides intelligence; the regulated institution remains
    responsible for policy, investigation, reporting, and fair decisions.

## Related Notes

- [Blockchain Analytics](blockchain-analytics.md)
- [Chainalysis and Elliptic](chainalysis-and-elliptic.md)
- [Crypto AML, Sanctions, and the Travel Rule](crypto-aml-sanctions-and-travel-rule.md)
- [Wallets, Key Management, and Digital-Asset Custody](../../03-digital-assets-and-market-structure/04-wallets-and-custody/wallets-key-management-and-digital-asset-custody.md)
- [Blockchain Interoperability and Bridges](../../06-interoperability-privacy-and-enterprise-dlt/01-interoperability/blockchain-interoperability-and-bridges.md)

## References

- TRM Labs, [Blockchain intelligence platform](https://www.trmlabs.com/blockchain-intelligence-platform)
- TRM Labs, [Wallet Screening](https://www.trmlabs.com/blockchain-intelligence-platform/wallet-screening)
- TRM Labs, [Transaction Monitoring](https://www.trmlabs.com/blockchain-intelligence-platform/transaction-monitoring)
- TRM Labs, [Forensics](https://www.trmlabs.com/blockchain-intelligence-platform/forensics)
- TRM Labs, [Blockchain coverage methodology](https://www.trmlabs.com/resources/blog/what-is-the-best-blockchain-intelligence-tool-in-2026)
- Merkle Science, [Platform and products](https://www.merklescience.com/)
- Merkle Science, [Attribution report](https://info.merklescience.com/attribution-report-2025)
- Merkle Science, [Tracker](https://www.merklescience.com/blog/major-enhancements-to-blockchain-investigation-tool)
- Chainalysis, [Blockchain Intelligence](https://www.chainalysis.com/blockchain-intelligence/)
- Chainalysis, [KYT](https://www.chainalysis.com/product/kyt/)
- Elliptic, [Blockchain analytics solutions](https://www.elliptic.co/solutions)
- GraphSense, [Open-source cryptoasset analytics](https://graphsense.org/)
- FATF, [Updated Guidance for a Risk-Based Approach to Virtual Assets and VASPs](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html)
- U.S. Department of the Treasury, [OFAC Sanctions Compliance Guidance for the Virtual Currency Industry](https://ofac.treasury.gov/media/913571/download)
