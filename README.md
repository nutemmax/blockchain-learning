# Blockchain, Digital Assets, Fintech, and Finance

A depth-first learning repository covering the financial system, blockchain
technology, digital-asset markets, DeFi, digital money, tokenization,
interoperability, privacy, enterprise DLT, regulation, analytics, and security.
It is written for technical readers learning finance and finance professionals
learning technical systems.

Canonical learning material lives under:

```text
notes/<macro-topic>/<micro-topic>/<note>.md
```

Each note is intended to be a long, self-contained teaching unit. The numbered
macro topics provide a suggested learning sequence; cross-links connect
prerequisites and related subjects.

## Repository Map

### 00 — Course Guide · `00-course-guide`

#### `01-orientation`

- [`glossary.md`](notes/00-course-guide/01-orientation/glossary.md) — Repository-wide definitions of specialized finance, regulatory, blockchain, infrastructure, protocol, product, and company terminology.

### 01 — Financial Foundations · `01-financial-foundations`

#### `01-money-banking-and-payments`

- [`money-banking-and-balance-sheets.md`](notes/01-financial-foundations/01-money-banking-and-payments/money-banking-and-balance-sheets.md) — Money, deposits, credit creation, bank balance sheets, reserves, liquidity, solvency, interest rates, and monetary transmission.
- [`payments-clearing-and-settlement.md`](notes/01-financial-foundations/01-money-banking-and-payments/payments-clearing-and-settlement.md) — Payment instruments and messages, clearing, netting, settlement, RTGS, cards, account-to-account payments, finality, and reconciliation.
- [`cross-border-payments-and-fx.md`](notes/01-financial-foundations/01-money-banking-and-payments/cross-border-payments-and-fx.md) — Correspondent banking, nostro and vostro accounts, FX, liquidity, CLS, settlement risk, fees, and cross-border payment models.

#### `02-financial-markets`

- [`financial-market-infrastructure.md`](notes/01-financial-foundations/02-financial-markets/financial-market-infrastructure.md) — Issuance, trading, clearing, CCPs, CSDs, custody, settlement, delivery versus payment, and reconciliation.
- [`securities-and-financial-instruments.md`](notes/01-financial-foundations/02-financial-markets/securities-and-financial-instruments.md) — Equity, debt, funds, derivatives, repos, securities lending, collateral, corporate actions, valuation, yield, and investor rights.
- [`market-microstructure-and-trading.md`](notes/01-financial-foundations/02-financial-markets/market-microstructure-and-trading.md) — Order books, liquidity, spreads, market makers, brokers, dealers, exchanges, OTC markets, execution quality, leverage, margin, and prime brokerage.

#### `03-risk-and-regulatory-foundations`

- [`financial-risk-management.md`](notes/01-financial-foundations/03-risk-and-regulatory-foundations/financial-risk-management.md) — Credit, market, liquidity, counterparty, settlement, model, operational, cyber, legal, and systemic risk, including controls and stress testing.
- [`financial-regulation-compliance-and-accounting.md`](notes/01-financial-foundations/03-risk-and-regulatory-foundations/financial-regulation-compliance-and-accounting.md) — Prudential and conduct regulation, KYC/AML, sanctions, securities and payments rules, accounting, capital, audit, and operational resilience.

### 02 — Blockchain Foundations · `02-blockchain-foundations`

#### `01-core-architecture`

- [`blockchain-fundamentals.md`](notes/02-blockchain-foundations/01-core-architecture/blockchain-fundamentals.md) — Ledgers, transactions, blocks, nodes, consensus, immutability, tokens, wallets, smart contracts, and foundational blockchain trade-offs.
- [`blockchain-architecture.md`](notes/02-blockchain-foundations/01-core-architecture/blockchain-architecture.md) — End-to-end blockchain architecture, component boundaries, transaction lifecycle, state, execution, networking, consensus, storage, and application access.
- [`cryptography-and-blockchain-data-structures.md`](notes/02-blockchain-foundations/01-core-architecture/cryptography-and-blockchain-data-structures.md) — Hashing, Merkle structures, signatures, commitments, key derivation, authenticated state, tries, and the limits of cryptographic guarantees.

#### `02-consensus-and-networks`

- [`consensus-mechanisms.md`](notes/02-blockchain-foundations/02-consensus-and-networks/consensus-mechanisms.md) — Proof of work, proof of stake, BFT designs, validator selection, incentives, attacks, safety, liveness, and consensus comparisons.
- [`peer-to-peer-networks-finality-and-forks.md`](notes/02-blockchain-foundations/02-consensus-and-networks/peer-to-peer-networks-finality-and-forks.md) — Peer discovery, propagation, mempools, block production, fork choice, finality, reorganizations, clients, nodes, and governance.

#### `03-execution-and-applications`

- [`smart-contracts-virtual-machines-and-token-standards.md`](notes/02-blockchain-foundations/03-execution-and-applications/smart-contracts-virtual-machines-and-token-standards.md) — Execution environments, gas, state transitions, contract calls, events, upgrades, account abstraction, token standards, and failure modes.
- [`oracles-indexers-and-offchain-data.md`](notes/02-blockchain-foundations/03-execution-and-applications/oracles-indexers-and-offchain-data.md) — Oracles, price feeds, proof of reserves, automation, RPC providers, explorers, indexers, The Graph, Dune, and offchain trust boundaries.

#### `04-scaling-and-modularity`

- [`blockchain-scaling-and-modular-architecture.md`](notes/02-blockchain-foundations/04-scaling-and-modularity/blockchain-scaling-and-modular-architecture.md) — Layer terminology, L1 scaling, channels, sidechains, rollups, sequencers, proofs, data availability, appchains, and modular systems.

#### `05-major-blockchains`

- [`bitcoin.md`](notes/02-blockchain-foundations/05-major-blockchains/bitcoin.md) — Bitcoin transactions, UTXOs, scripts, mining, consensus, networking, monetary policy, wallets, scaling, governance, and security.
- [`ethereum.md`](notes/02-blockchain-foundations/05-major-blockchains/ethereum.md) — Ethereum accounts, EVM execution, gas, proof of stake, validators, transactions, smart contracts, scaling, economics, and roadmap.
- [`alternative-layer-1s-and-appchains.md`](notes/02-blockchain-foundations/05-major-blockchains/alternative-layer-1s-and-appchains.md) — Solana, Avalanche, Cosmos, Polkadot, Cardano, Algorand, Sui, Aptos, and appchain designs compared across their principal architectural choices.

### 03 — Digital Assets and Market Structure · `03-digital-assets-and-market-structure`

#### `01-assets-and-economics`

- [`digital-assets-token-taxonomy-and-economics.md`](notes/03-digital-assets-and-market-structure/01-assets-and-economics/digital-assets-token-taxonomy-and-economics.md) — Native assets, utility and governance tokens, security-like claims, wrapped assets, NFTs, issuance, supply, vesting, incentives, valuation, and legal rights.

#### `02-centralized-markets`

- [`crypto-market-structure-and-centralized-exchanges.md`](notes/03-digital-assets-and-market-structure/02-centralized-markets/crypto-market-structure-and-centralized-exchanges.md) — Centralized spot and derivatives venues, order books, internal ledgers, market makers, on/off-ramps, custody, proof of reserves, surveillance, and counterparty risk.
- [`coinbase.md`](notes/03-digital-assets-and-market-structure/02-centralized-markets/coinbase.md) — Coinbase's history, legal and business structure, retail and institutional products, custody, Base, USDC economics, staking, payments, regulation, financial model, and risks.

#### `03-decentralized-markets`

- [`decentralized-exchanges-and-automated-market-makers.md`](notes/03-digital-assets-and-market-structure/03-decentralized-markets/decentralized-exchanges-and-automated-market-makers.md) — AMM curves, concentrated liquidity, routing, slippage, impermanent loss, LP economics, MEV, governance, and Uniswap, Curve, Balancer, and CoW Protocol.
- [`onchain-order-books-and-derivatives-venues.md`](notes/03-digital-assets-and-market-structure/03-decentralized-markets/onchain-order-books-and-derivatives-venues.md) — Onchain order books, perpetual futures, funding, margin, liquidation, insurance funds, sequencers, appchains, and venues such as dYdX, Hyperliquid, and GMX.

#### `04-wallets-and-custody`

- [`wallets-key-management-and-digital-asset-custody.md`](notes/03-digital-assets-and-market-structure/04-wallets-and-custody/wallets-key-management-and-digital-asset-custody.md) — Keys, addresses, seed phrases, HD wallets, HSMs, MPC/TSS, multisig, custody models, segregation, policies, recovery, and legal ownership.
- [`institutional-custody-and-wallet-infrastructure.md`](notes/03-digital-assets-and-market-structure/04-wallets-and-custody/institutional-custody-and-wallet-infrastructure.md) — Institutional custody architecture and neutral studies of Fireblocks, BitGo, Copper, Anchorage, Taurus, Coinbase Custody, Fidelity, and bank custodians.

### 04 — Decentralized Finance · `04-decentralized-finance`

#### `01-defi-foundations`

- [`defi-architecture-composability-and-governance.md`](notes/04-decentralized-finance/01-defi-foundations/defi-architecture-composability-and-governance.md) — DeFi primitives, atomicity, composability, liquidity, governance, incentives, front ends, keepers, oracles, upgrades, and protocol-company distinctions.

#### `02-onchain-lending`

- [`onchain-lending-and-credit.md`](notes/04-decentralized-finance/02-onchain-lending/onchain-lending-and-credit.md) — Pooled and isolated lending, collateral, interest-rate models, health factors, liquidations, bad debt, flash loans, vault curators, and credit risk.
- [`aave.md`](notes/04-decentralized-finance/02-onchain-lending/aave.md) — Aave's architecture, reserves, rates, risk parameters, eMode, isolation, liquidations, governance, safety mechanisms, GHO, deployments, and risks.
- [`morpho.md`](notes/04-decentralized-finance/02-onchain-lending/morpho.md) — Morpho's protocol evolution, isolated markets, LLTV, oracles, interest-rate models, vaults, curators, governance, integrations, and risk allocation.
- [`sky-maker-spark.md`](notes/04-decentralized-finance/02-onchain-lending/sky-maker-spark.md) — MakerDAO and Sky, DAI and USDS, vaults, collateral, liquidations, savings, real-world assets, governance, Spark, and system risks.
- [`other-onchain-credit-protocols.md`](notes/04-decentralized-finance/02-onchain-lending/other-onchain-credit-protocols.md) — Compound, Euler, Liquity, Maple, Centrifuge, and other lending and onchain-credit designs.

#### `03-derivatives-staking-and-yield`

- [`onchain-derivatives-structured-products-and-yield.md`](notes/04-decentralized-finance/03-derivatives-staking-and-yield/onchain-derivatives-structured-products-and-yield.md) — Perpetuals, options, synthetics, basis and funding trades, structured vaults, yield sources, leverage, recursive positions, and risk.
- [`staking-liquid-staking-and-restaking.md`](notes/04-decentralized-finance/03-derivatives-staking-and-yield/staking-liquid-staking-and-restaking.md) — Native and liquid staking, validator economics, slashing, Lido, Rocket Pool, EigenLayer, liquid restaking, and correlated risk.

#### `04-defi-risk-and-failures`

- [`defi-risk-security-and-economic-attacks.md`](notes/04-decentralized-finance/04-defi-risk-and-failures/defi-risk-security-and-economic-attacks.md) — Smart-contract, governance, oracle, liquidity, liquidation, bridge, MEV, stablecoin, composability, and operational risks, with mitigations and incidents.

### 05 — Digital Money and Tokenization · `05-digital-money-and-tokenization`

#### `01-stablecoins`

- [`stablecoins.md`](notes/05-digital-money-and-tokenization/01-stablecoins/stablecoins.md) — Stablecoin definitions, legal claims, issuance, redemption, reserves, stabilization models, use cases, depegs, runs, regulation, accounting, and comparisons with other money forms.
- [`stablecoin-issuers-and-protocols.md`](notes/05-digital-money-and-tokenization/01-stablecoins/stablecoin-issuers-and-protocols.md) — Circle/USDC, Tether/USDT, Paxos, Sky/DAI/USDS, Aave/GHO, Ethena/USDe, Liquity, PayPal/PYUSD, and other issuer and protocol models.

#### `02-cbdcs-and-bank-money`

- [`central-bank-digital-currencies.md`](notes/05-digital-money-and-tokenization/02-cbdcs-and-bank-money/central-bank-digital-currencies.md) — Retail and wholesale CBDCs, issuance models, architecture, privacy, monetary policy, financial stability, cross-border work, and major pilots.
- [`tokenized-deposits-and-commercial-bank-money.md`](notes/05-digital-money-and-tokenization/02-cbdcs-and-bank-money/tokenized-deposits-and-commercial-bank-money.md) — Bank-money claims, issuance and redemption, deposit insurance, interbank settlement, programmability, interoperability, and examples.

#### `03-tokenized-assets`

- [`tokenization-of-securities-funds-and-real-world-assets.md`](notes/05-digital-money-and-tokenization/03-tokenized-assets/tokenization-of-securities-funds-and-real-world-assets.md) — Token representation and native issuance, legal wrappers, registries, identity, lifecycle events, custody, cash legs, delivery versus payment, and risks.
- [`tokenization-platforms-and-market-case-studies.md`](notes/05-digital-money-and-tokenization/03-tokenized-assets/tokenization-platforms-and-market-case-studies.md) — Securitize, Ondo, Centrifuge, Franklin Templeton, BUIDL, JPMorgan, Société Générale-FORGE, and other tokenization cases.

### 06 — Interoperability, Privacy, and Enterprise DLT · `06-interoperability-privacy-and-enterprise-dlt`

#### `01-interoperability`

- [`blockchain-interoperability-and-bridges.md`](notes/06-interoperability-privacy-and-enterprise-dlt/01-interoperability/blockchain-interoperability-and-bridges.md) — Cross-chain messaging and assets, bridge models, proofs, validator networks, intents, atomic swaps, finality, replay protection, fragmentation, and failures.
- [`layerzero.md`](notes/06-interoperability-privacy-and-enterprise-dlt/01-interoperability/layerzero.md) — LayerZero endpoints, message libraries, DVNs, executors, application-selected security, omnichain tokens, trust assumptions, and limitations.
- [`interoperability-protocols.md`](notes/06-interoperability-privacy-and-enterprise-dlt/01-interoperability/interoperability-protocols.md) — Chainlink CCIP, Axelar, Wormhole, Cosmos IBC, Polkadot XCM, and other designs compared by verification, execution, governance, and failure model.

#### `02-privacy`

- [`privacy-and-confidential-computing-for-blockchains.md`](notes/06-interoperability-privacy-and-enterprise-dlt/02-privacy/privacy-and-confidential-computing-for-blockchains.md) — Pseudonymity, zero-knowledge proofs, commitments, MPC, trusted execution, FHE, selective disclosure, confidential tokens, privacy pools, and metadata leakage.
- [`zama.md`](notes/06-interoperability-privacy-and-enterprise-dlt/02-privacy/zama.md) — FHE and TFHE, fhEVM, encrypted state, coprocessors, gateways, key management, threshold decryption, access control, performance, and trust assumptions.
- [`paladin.md`](notes/06-interoperability-privacy-and-enterprise-dlt/02-privacy/paladin.md) — Paladin's EVM privacy architecture, privacy groups, Pente, Zeto, Noto, notaries, private state, atomic interoperability, deployment, and limitations.

#### `03-enterprise-dlt`

- [`enterprise-ethereum-and-hyperledger.md`](notes/06-interoperability-privacy-and-enterprise-dlt/03-enterprise-dlt/enterprise-ethereum-and-hyperledger.md) — Enterprise Ethereum, Besu, permissioning, private transactions, FireFly, Cacti, identity, operations, and workflow architecture.
- [`canton-corda-and-institutional-ledgers.md`](notes/06-interoperability-privacy-and-enterprise-dlt/03-enterprise-dlt/canton-corda-and-institutional-ledgers.md) — Canton, Daml, Corda, privacy and synchronization, asset workflows, permissioning, governance, and institutional-ledger comparisons.

### 07 — Compliance, Analytics, Regulation, and Security · `07-compliance-analytics-regulation-and-security`

#### `01-aml-and-blockchain-analytics`

- [`blockchain-analytics.md`](notes/07-compliance-analytics-regulation-and-security/01-aml-and-blockchain-analytics/blockchain-analytics.md) — Analytics pipelines, transaction graphs, clustering, attribution, exposure, scoring, cross-chain tracing, DeFi decoding, monitoring, and model limitations.
- [`chainalysis-and-elliptic.md`](notes/07-compliance-analytics-regulation-and-security/01-aml-and-blockchain-analytics/chainalysis-and-elliptic.md) — Neutral technical comparison of Chainalysis and Elliptic products, workflows, APIs, evidence, documented architecture, strengths, and limitations.
- [`trm-labs-merkle-science-and-analytics-landscape.md`](notes/07-compliance-analytics-regulation-and-security/01-aml-and-blockchain-analytics/trm-labs-merkle-science-and-analytics-landscape.md) — TRM Labs, Merkle Science, Scorechain, Crystal, Coinfirm, Arkham, Nansen, and the wider compliance and market-analytics landscape.
- [`crypto-aml-sanctions-and-travel-rule.md`](notes/07-compliance-analytics-regulation-and-security/01-aml-and-blockchain-analytics/crypto-aml-sanctions-and-travel-rule.md) — KYC/KYB, transaction screening, sanctions, source of funds, typologies, Travel Rule, unhosted wallets, investigations, reporting, and false positives.

#### `02-regulation`

- [`digital-asset-regulation.md`](notes/07-compliance-analytics-regulation-and-security/02-regulation/digital-asset-regulation.md) — Regulatory perimeter, asset classification, issuance, trading, custody, stablecoins, DeFi, market abuse, licensing, prudential treatment, tax, and jurisdictional comparisons.

#### `03-security-and-case-studies`

- [`blockchain-smart-contract-and-operational-security.md`](notes/07-compliance-analytics-regulation-and-security/03-security-and-case-studies/blockchain-smart-contract-and-operational-security.md) — Protocol, consensus, bridge, contract, wallet, custody, API, key-management, governance, insider, supply-chain, and operational security.
- [`digital-asset-failures-and-lessons.md`](notes/07-compliance-analytics-regulation-and-security/03-security-and-case-studies/digital-asset-failures-and-lessons.md) — Sourced exchange, lender, stablecoin, bridge, protocol, custody, and governance failures, separating facts, causes, and lessons.