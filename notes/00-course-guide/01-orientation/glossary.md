# Glossary

This glossary gives concise working definitions for recurring terms. Complex
mechanisms, legal distinctions, and trade-offs require the fuller explanations
in the related topic notes. Definitions involving law or regulation are general
and can vary by jurisdiction and date.

## Money, Banking, and Financial Plumbing

| Term | Explanation |
|---|---|
| **Asset** | Something with economic value, or a claim on economic value. Examples: cash, a bank deposit, a stock, a bond, ETH, a tokenized Treasury claim. |
| **Liability** | Something an entity owes to someone else. A bank deposit is an asset for the customer but a liability for the bank, because the bank owes the customer money on demand. |
| **Digital money** | Money represented and transferred electronically. This includes normal bank deposits, e-money balances, stablecoins, tokenized deposits, and CBDCs. The key question is always: **who issued it, whose liability is it, what backs it, and how can it be redeemed?** |
| **Commercial bank money** | Money created by commercial banks, mainly customer deposits. If your bank app says you have $1,000, that is not physical cash sitting in a box; it is the bank's promise to pay you $1,000. |
| **Central bank money** | Money that is a direct liability of the central bank. Physical cash and commercial-bank reserves at the central bank are central bank money. It is usually the safest settlement asset in a currency system. |
| **Central bank reserves** | Balances that commercial banks hold at the central bank. Regular people usually cannot hold reserves directly. Banks use reserves to settle obligations with each other. |
| **Deposit** | Money a customer places at a bank. Legally and economically, a deposit is a claim on the bank, not a segregated pile of cash. The bank can use deposits to fund loans and investments, subject to regulation and liquidity rules. |
| **Deposit insurance** | A government or agency guarantee that protects bank deposits up to a limit if a bank fails. This is one reason insured bank deposits feel safer than uninsured stablecoins or exchange balances. |
| **E-money** | Digital money issued by a regulated non-bank payment institution. It is usually backed by safeguarded funds, but it is not the same as a bank deposit and usually does not create credit like bank lending does. Examples: some PayPal, Wise, or prepaid payment balances depending on jurisdiction and product. |
| **Settlement** | The final transfer of money or assets that completes a transaction. Buying a stock and seeing it in an app is not always final settlement; settlement is when legal ownership and payment are actually completed. |
| **Clearing** | The process after trades are agreed but before final settlement. Clearing calculates who owes what, nets obligations where possible, and manages risk if someone fails before settlement. |
| **T+1 / T+2 / T+0** | Settlement timing. `T+1` means settlement happens one business day after trade date. `T+0` means same-day settlement. Blockchain systems often aim for faster settlement, but legal and operational finality still matter. |
| **Counterparty risk** | The risk that the other party in a transaction fails to deliver what they owe. Example: you deliver securities but the buyer fails to pay, or you hold funds at an exchange that becomes insolvent. |
| **Custody** | Safekeeping and control of assets. In TradFi, custody usually means a regulated institution safeguards securities and records ownership. In crypto, custody usually means control over private keys that can move assets on-chain. The core question is: **who can actually move the asset?** |
| **Custodian** | An institution or service that safeguards assets for clients. In TradFi, custodians hold securities and maintain ownership records. In crypto, custodians safeguard private keys or operate wallets controlling on-chain assets. |
| **Broker** | An intermediary that helps clients buy or sell assets. A broker acts for customers; it does not necessarily trade for its own account. |
| **Dealer** | A firm that buys and sells assets for its own account, often holding inventory. A broker-dealer can do both client execution and principal trading. |
| **Market maker** | A firm or mechanism that continuously provides buy and sell prices. Market makers improve liquidity by standing ready to trade, earning from spreads or fees while taking inventory risk. |
| **Liquidity** | How easy it is to buy or sell an asset without moving its price much. A liquid market has many buyers/sellers, tight bid-ask spreads, and enough depth for large trades. |
| **Bid-ask spread** | The gap between the highest price buyers offer and the lowest price sellers accept. A tight spread usually means better liquidity and lower trading cost. |
| **NAV (Net Asset Value)** | The value of a fund's assets minus liabilities, usually divided by the number of shares. If a fund holds $100 million of assets and has 10 million shares, NAV is about $10 per share. |
| **Basis point (bps)** | One hundredth of one percent: `1 bp = 0.01%`. A 25 bps fee means `0.25%`. Finance uses bps because small percentage differences matter. |
| **Yield** | Income return on an asset, usually annualized. Examples: bond interest, bank deposit interest, lending protocol interest, staking rewards. Yield is not the same as total return because asset prices can also rise or fall. |
| **Collateral** | An asset pledged to secure an obligation. If the borrower fails to repay, the lender can seize or sell the collateral. Example: posting ETH to borrow a stablecoin in DeFi. |
| **Margin** | Borrowed money or collateral used to increase trading exposure. Margin can amplify gains, but it also increases liquidation risk. |
| **Leverage** | Using borrowed funds or derivatives to control more exposure than your own capital alone would allow. Example: with 3x leverage, a 10% adverse move can wipe out roughly 30% of equity before fees and liquidation effects. |
| **Liquidation** | Forced sale or seizure of collateral when its value falls too low relative to a loan or leveraged position. In DeFi, liquidation is often automatic through smart contracts. |
| **Reserve** | Assets held to back liabilities or meet withdrawals. For a bank, reserves may mean central bank balances or liquid assets; for a stablecoin issuer, reserves usually mean cash-like assets backing token redemption. |
| **Fractional-reserve banking** | Banking model where banks keep only part of deposits in immediately liquid form and use the rest to make loans or buy assets. This supports credit creation but creates liquidity risk if too many depositors withdraw at once. |
| **Central bank** | The institution that issues sovereign money, sets monetary policy, supports the banking system, and often operates or oversees core payment systems. Examples: Federal Reserve, ECB, Swiss National Bank. |
| **Monetary policy** | Central bank actions that influence interest rates, credit, inflation, and economic activity. The most visible tool is setting short-term interest rates. |
| **Fiat currency** | Government-issued money not backed by a commodity like gold. Its value comes from legal status, tax/payment usefulness, central bank credibility, and social acceptance. Examples: USD, EUR, CHF. |
| **Legal tender** | Money that must be accepted to settle certain debts under law in a jurisdiction. Legal tender status does not mean every merchant must accept every payment form in every context. |
| **Peg** | A target exchange rate between one asset and another. A USD stablecoin targets `1 token = $1`. The peg can be maintained by reserves, arbitrage, issuer redemption, collateral, or algorithmic mechanisms. |
| **De-peg** | When a pegged asset trades away from its target. Example: a $1 stablecoin trading at $0.97 has de-pegged. De-pegs can happen because of reserve doubts, redemption friction, market panic, or protocol failure. |
| **KYC / AML** | Know Your Customer / Anti-Money Laundering controls. Financial institutions verify customer identity and monitor suspicious activity to comply with law and reduce illicit-finance risk. |
| **Institutional investor** | A large professional investor such as a pension fund, insurance company, bank, hedge fund, endowment, sovereign wealth fund, or asset manager. Institutions usually need regulated custody, compliance, reporting, and risk controls before holding crypto assets. |
| **AUM (Assets Under Management)** | Total market value of assets managed by a firm or fund for clients. AUM is a scale metric, not a measure of profit or safety. |

## Blockchain Foundations

| Term | Explanation |
|---|---|
| **DLT (Distributed Ledger Technology)** | A ledger replicated across multiple computers that coordinate to keep a shared record. A blockchain is one type of DLT where records are grouped into cryptographically linked blocks. Not every DLT is literally a blockchain. |
| **Blockchain** | A replicated ledger where transactions are grouped into blocks, and each block references earlier blocks using cryptographic hashes. This creates a tamper-evident history that many nodes can independently verify. |
| **Node** | A computer participating in a blockchain or DLT network. Nodes may store data, relay transactions, verify blocks, propose blocks, or serve data to users. Not every node has the same role. |
| **Transaction** | A signed instruction that changes ledger state. Example: "move 10 USDC from address A to address B" or "call this smart contract function." |
| **Block** | A batch of transactions plus metadata, such as timestamp, previous block reference, and consensus-specific data. Blocks make the ledger easier to order, verify, and replicate. |
| **State** | The current condition of the ledger after all valid transactions so far. Examples: account balances, smart contract storage, token ownership, validator set. |
| **Smart contract** | Code deployed on a blockchain that can hold assets, store state, and execute rules when called by transactions. Example: a lending smart contract can hold collateral, calculate loan health, and allow liquidation if collateral falls below a threshold. Smart contracts reduce reliance on human operators but create code, oracle, governance, and legal risks. |
| **Gas** | The fee paid to make a blockchain execute a transaction or smart contract call. Simple transfer = less gas; complex DeFi interaction = more gas. Example: sending ETH may require one basic state update, while swapping on a DEX may call multiple contracts, update pool balances, and emit events, so it costs more. Gas prevents spam and pays validators/miners for including and executing transactions. |
| **Oracle** | A service that brings external data onto a blockchain, such as asset prices, interest rates, or event outcomes. Blockchains cannot directly know off-chain facts, so DeFi often relies on oracles. Bad oracle data can break otherwise-correct smart contracts. |
| **Bridge** | Infrastructure that moves value or messages between blockchains. Usually it locks or verifies an asset on one chain and mints or releases a representation on another. Bridges are useful for interoperability but historically high-risk because they concentrate technical and custody assumptions. |
| **Wallet** | Software or hardware that manages private keys and helps users sign transactions. A wallet does not literally store coins; assets are recorded on the ledger, while the wallet controls the keys needed to move them. |
| **Private key** | A secret cryptographic value that lets you authorize transactions. Whoever controls the private key can usually control the assets at the related address. Losing it can mean permanent loss of access. |
| **Public key** | A cryptographic value derived from a private key and used to verify signatures. It can be shared publicly. |
| **Address** | A shorter identifier derived from public-key material, used like an account destination on a blockchain. Example: someone sends tokens to your address, but you need the private key to move them later. |
| **Digital signature** | A cryptographic proof that a transaction was authorized by the holder of a private key, without revealing the private key itself. It is how blockchains verify ownership and authorization. |
| **Hash** | A fixed-length fingerprint of data. If the input changes even slightly, the hash changes unpredictably. Hashes are used to link blocks, identify data, build Merkle trees, and make tampering detectable. |
| **Merkle tree** | A data structure that hashes many pieces of data into one root hash. It lets someone prove a transaction is included in a block without downloading every transaction. |
| **Fork** | A split in blockchain history or protocol rules. Temporary forks can happen naturally when two valid blocks appear close together. Permanent forks happen when communities or validators adopt incompatible rules. |
| **Finality** | The point at which a transaction is treated as irreversible. Some systems have probabilistic finality, where reversal becomes increasingly unlikely over time; others have deterministic finality, where a block is final once enough validators sign it. |

## Consensus and Network Security

| Term | Explanation |
|---|---|
| **Consensus** | The process a distributed network uses to agree on the valid ledger history and current state even when some participants are offline, slow, or malicious. It answers: **which transactions count, in what order, and who gets to add the next block?** |
| **Consensus mechanism** | The concrete protocol for reaching consensus. It combines networking rules, validator/miner selection, incentives, penalties, and fork-choice/finality rules. Main families include Proof of Work, Proof of Stake, and BFT-style consensus. |
| **Proof of Work (PoW)** | Consensus where miners compete to solve computational puzzles by hashing. The first miner to find a valid block earns rewards. Security comes from the real-world cost of hardware and electricity. Bitcoin uses PoW. |
| **Proof of Stake (PoS)** | Consensus where validators lock up native tokens as stake and are selected to propose or attest to blocks. Security comes from capital at risk: dishonest validators can lose stake through slashing. Ethereum uses PoS. |
| **Delegated Proof of Stake (DPoS)** | PoS variant where token holders vote for a smaller set of validators or block producers. It can be faster and simpler to coordinate, but may concentrate power among a few large operators. |
| **Proof of Authority (PoA)** | Consensus where a known, approved set of validators produces blocks based on identity/reputation rather than open mining or broad staking. Common in private or permissioned networks. It is efficient but less decentralized. |
| **Proof of Capacity / Proof of Space (PoC)** | Consensus where participants commit storage capacity rather than computation or stake. Security relies on proving that storage space has been allocated. Chia popularized a related proof-of-space-and-time model. |
| **BFT-style consensus** | Consensus family designed to tolerate Byzantine faults, meaning some validators may lie, fail, or send conflicting messages. Validators exchange votes and can finalize blocks if enough agree, commonly assuming less than one-third are malicious. Used often in permissioned or validator-set-based systems. |
| **Nakamoto consensus** | Bitcoin-style consensus combining PoW, blocks, and the longest/heaviest-chain rule. It gives probabilistic finality: deeper blocks are harder to reverse because an attacker must redo increasing work. |
| **Byzantine Fault Tolerance (BFT)** | A system property: the network can still agree correctly even if some participants behave maliciously or inconsistently. "Byzantine" means arbitrary bad behavior, not just being offline. |
| **Validator** | A participant that checks transactions and participates in consensus, usually in PoS or BFT systems. Validators may propose blocks, vote on blocks, and earn rewards. |
| **Miner** | A participant in PoW consensus that performs hashing work to propose blocks. Miners earn block rewards and fees when they produce accepted blocks. |
| **Slashing** | A PoS penalty where a validator loses some staked assets for provable misbehavior, such as double-signing conflicting blocks. Slashing turns dishonest behavior into an economic loss. |
| **51% attack** | An attack where one actor controls enough mining power, stake, or validator influence to rewrite recent history, censor transactions, or manipulate ordering. The exact threshold and consequences depend on the consensus design. |

## Tokens, Digital Assets, and Tokenization

| Term | Explanation |
|---|---|
| **Digital asset** | A digitally represented asset, claim, or right. It may be native to a blockchain, like BTC, or represent something external, like a tokenized bond. |
| **Token** | A digital unit recorded on a blockchain or ledger. Tokens can represent money-like claims, governance rights, access rights, collateral, securities, collectibles, or other assets. |
| **Coin / native asset** | The asset native to a blockchain, usually used for fees, incentives, or security. Examples: BTC on Bitcoin, ETH on Ethereum, SOL on Solana. |
| **Minting** | Creating new units of a token or asset. Example: when a stablecoin issuer receives $1,000 from a customer and creates 1,000 new stablecoin tokens, it has minted tokens. Minting increases supply. |
| **Burning** | Destroying tokens or removing them permanently from circulation. Example: when a user redeems 1,000 stablecoins for $1,000, the issuer may burn the returned tokens so supply decreases. |
| **Tokenized asset** | A token that represents a claim on, ownership interest in, or economic exposure to an asset. Examples: tokenized Treasury funds, tokenized bonds, tokenized deposits, tokenized real estate shares. The hard part is not only technical; the token must also map to enforceable legal rights. |
| **RWA (Real-World Asset)** | An off-chain asset represented on-chain. Examples: Treasury bills, private credit, real estate, invoices, commodities. RWA tokens depend on legal structure, custody, valuation, and issuer reliability. |
| **Tokenization** | The process of representing an asset, claim, or right as a digital token. Tokenization can make transfer, settlement, and programmability easier, but it does not magically remove legal, custody, or credit risk. |
| **Wrapped asset** | A token on one chain representing an asset from another chain or system. Example: wrapped BTC on Ethereum represents BTC locked or controlled elsewhere. Main risk: the wrapper must be trusted or verified. |
| **Governance token** | A token that gives voting power over protocol parameters, treasury spending, upgrades, or governance decisions. It may not provide the same legal rights as corporate equity. |
| **Utility token** | A token intended to provide access to a product or service. The label does not automatically determine legal treatment; if buyers expect profit from others' efforts, regulators may still scrutinize it. |

## Stablecoins, CBDCs, and Digital Money Forms

| Term | Explanation |
|---|---|
| **Stablecoin** | A token designed to keep a stable value relative to a reference asset, usually `1 token = 1 USD`. A fiat-backed stablecoin normally works like this: users send dollars to an issuer, the issuer holds reserves, mints tokens, and later redeems tokens for dollars. The stablecoin is only as reliable as its reserves, redemption process, legal structure, issuer, and market confidence. |
| **Fiat-backed stablecoin** | A stablecoin backed by cash, bank deposits, Treasury bills, or similar assets. Example flow: deposit $100 with issuer -> issuer mints 100 tokens -> tokens circulate on-chain -> holder redeems 100 tokens -> issuer pays $100 and burns tokens. Main risks: reserve quality, issuer solvency, redemption delays, regulation, bank exposure. |
| **Crypto-collateralized stablecoin** | A stablecoin backed by crypto collateral locked in smart contracts, usually overcollateralized because crypto prices are volatile. Example: lock $150 of ETH to mint/borrow $100 of stablecoin. Main risks: collateral crashes, oracle failure, liquidation failure, governance risk. |
| **Algorithmic stablecoin** | A stablecoin that tries to maintain a peg mainly through incentives, supply changes, or linked tokens rather than full external reserves. These designs are fragile because confidence can collapse if the mechanism cannot absorb redemptions or selling pressure. |
| **Payment stablecoin** | A stablecoin designed primarily for payments and transfers rather than investment. It should maintain stable value, be redeemable, and have reliable reserves. Exact legal meaning depends on jurisdiction and date. |
| **CBDC (Central Bank Digital Currency)** | Digital money issued directly by a central bank. A CBDC is a direct central bank liability, unlike a stablecoin, which is usually a private issuer liability, or a bank deposit, which is a commercial bank liability. |
| **Retail CBDC** | A CBDC available to households and businesses. It could function like digital cash, but raises policy questions around privacy, bank deposit outflows, payment competition, and state control. |
| **Wholesale CBDC** | A CBDC available only to banks or financial institutions, mainly for interbank settlement or settlement of tokenized assets. It is less visible to consumers but important for institutional market infrastructure. |
| **Tokenized deposit** | A bank deposit represented as a token. The holder still has a claim on the commercial bank, similar to a normal deposit, but transfer and settlement may happen on shared ledger infrastructure. Difference from stablecoin: a tokenized deposit is bank money; a stablecoin is usually non-bank private issuer money. |
| **Singleness of money** | The principle that different safe forms of the same currency should trade at par: $1 in cash, $1 in a bank deposit, and $1 in a well-functioning stable money instrument should be worth $1. Breaks in singleness show up as de-pegs, discounts, or loss of confidence. |
| **Redemption** | Exchanging a token or claim back for the underlying asset or money. For stablecoins, redemption means returning tokens to the issuer and receiving fiat money. Redemption rights and practical access matter more than the headline peg. |
| **Reserve backing** | Assets held to support redemption of issued money-like claims. For stablecoins, high-quality liquid reserves make it easier to meet redemptions. Poor, risky, opaque, or illiquid reserves make a run more dangerous. |

### Stablecoins vs CBDCs

| Feature | Stablecoin | CBDC |
|---|---|---|
| Issuer | Private issuer, often a company or protocol | Central bank |
| Liability of | Stablecoin issuer, or smart-contract system for decentralized designs | Central bank |
| Typical backing | Cash, bank deposits, Treasuries, crypto collateral, or mechanism design | Sovereign central bank balance sheet |
| Main use | On-chain payments, trading, DeFi, cross-border transfers, dollar access | Public money, payment infrastructure, interbank/tokenized asset settlement |
| Key risks | Reserve risk, issuer risk, redemption risk, smart contract risk, regulation | Privacy, bank disintermediation, policy design, operational resilience |
| Simple intuition | A private digital dollar-like claim | Central bank money in digital form |

## DeFi and Market Infrastructure

| Term | Explanation |
|---|---|
| **DeFi (Decentralized Finance)** | Financial applications built with smart contracts and on-chain settlement. DeFi can provide trading, lending, borrowing, derivatives, and asset management without traditional intermediaries, but it introduces smart contract, oracle, governance, liquidity, and MEV risks. |
| **CEX (Centralized Exchange)** | A crypto exchange run by a company. Users often deposit assets into the exchange's custody, and trades happen in the exchange's internal systems. Examples: Coinbase, Kraken, Binance. Main risks: custody, solvency, operational controls, regulation. |
| **DEX (Decentralized Exchange)** | An exchange implemented through smart contracts. Users trade from their own wallets, often against liquidity pools. Examples: Uniswap, Curve. Main risks: smart contracts, MEV, oracle/pricing issues, and poor liquidity for some assets. |
| **AMM (Automated Market Maker)** | A DEX mechanism where prices are set by a formula rather than a traditional order book. In a simple `x * y = k` pool, buying one asset removes it from the pool and adds the other, pushing price along a curve. |
| **Liquidity provider (LP)** | A user or institution that supplies assets to a market so others can trade or borrow. In an AMM, an LP deposits pairs such as ETH and USDC into a pool and earns fees. Risks include price movement, impermanent loss, smart contract bugs, and withdrawal during stressed markets. |
| **Liquidity pool** | A smart contract holding assets supplied by liquidity providers. Traders swap against the pool instead of matching directly with another trader. Pool balances determine prices in many AMM designs. |
| **Impermanent loss** | Loss an AMM liquidity provider can experience when the relative prices of deposited assets change. It is "impermanent" only if prices later return; otherwise it is economically real. Fees may or may not compensate for it. |
| **MEV (Maximal Extractable Value)** | Value extracted by controlling or influencing transaction ordering within a block. Example: a bot sees a large DEX trade, buys before it, lets the user's trade move the price, then sells after it. This is called a sandwich attack. |
| **TVL (Total Value Locked)** | The dollar value of assets deposited in a DeFi protocol. It is a rough size metric, similar in spirit to AUM, but can be inflated, double-counted, or misleading. |
| **DAO (Decentralized Autonomous Organization)** | A governance structure where rules, treasury decisions, or protocol changes are managed through code and token-holder voting. In practice, DAOs often still depend on core teams, legal wrappers, delegates, and off-chain coordination. |

## Regulation and Classification

| Term | Explanation |
|---|---|
| **SEC** | US Securities and Exchange Commission. Regulates securities markets, investment products, disclosures, and many intermediaries. Crypto disputes often involve whether a token or product is a security. |
| **CFTC** | US Commodity Futures Trading Commission. Regulates derivatives markets and has authority over commodity derivatives and certain anti-fraud/anti-manipulation matters in commodity spot markets. |
| **Howey test** | US legal test for whether something is an investment contract, and therefore a security. In simplified form: investment of money, in a common enterprise, with expectation of profit, mainly from others' efforts. It is often applied to token sales. |
| **Security token** | A token representing a security-like legal claim, such as equity, debt, revenue share, or fund interest. It must usually follow securities laws even if issued on a blockchain. |
| **Commodity** | A broad category of tradable goods or assets. In crypto, BTC is commonly treated as a commodity in the US regulatory context, but classification can depend on asset, facts, jurisdiction, and date. |
| **Travel Rule** | AML rule requiring certain financial institutions and crypto asset service providers to transmit originator and beneficiary information for qualifying transfers. Exact thresholds and implementation vary by jurisdiction. |

## Custody Types

| Type | Simple meaning | Example | Pros | Risks / trade-offs |
|---|---|---|---|---|
| **Self-custody** | You control the private keys yourself. | Hardware wallet or self-managed software wallet. | Maximum direct control; no exchange or custodian can freeze or misuse assets by itself. | Lose the key or seed phrase and you may lose assets permanently; phishing and operational mistakes are your responsibility. |
| **Third-party custody** | A company controls keys or asset movement for you. | Crypto exchange account or institutional crypto custodian. | Easier recovery, compliance, reporting, institutional controls. | You take custodian solvency, operational, legal, and counterparty risk. |
| **Qualified / regulated custody** | A regulated custodian holds assets under specific legal and operational rules. | Institutional digital asset custody provider or bank custody service. | Better fit for institutions, audits, segregation, controls, insurance possibilities. | More expensive; may restrict asset access, DeFi use, or transfer speed. |
| **Multi-signature custody** | Asset movement requires multiple keys to approve. | 2-of-3 wallet requiring user, backup, and service provider signatures. | Reduces single-key failure; useful for teams and treasuries. | More operational complexity; bad key governance can still block access. |
| **MPC custody** | Private-key control is split into cryptographic shares, so no one party holds the full key. | Institutional wallet infrastructure using distributed signing. | Strong operational security; flexible approval workflows. | More complex; relies on correct implementation and vendor/process controls. |

## References

- CPMI-IOSCO, [Principles for Financial Market Infrastructures](https://www.bis.org/cpmi/publ/d101.htm), 2012.
- Bank for International Settlements, [The monetary system of the future: from vision to reality](https://www.bis.org/publ/arpdf/ar2025e3.htm), 2025.
- Financial Action Task Force, [Virtual assets](https://www.fatf-gafi.org/en/topics/virtual-assets.html).
- National Institute of Standards and Technology, [Blockchain Technology Overview (NISTIR 8202)](https://csrc.nist.gov/pubs/ir/8202/final), 2018.
- Satoshi Nakamoto, [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf), 2008.
- Ethereum.org, [Ethereum development documentation](https://ethereum.org/developers/docs/).
- U.S. Securities and Exchange Commission, [Framework for “Investment Contract” Analysis of Digital Assets](https://www.sec.gov/corpfin/framework-investment-contract-analysis-digital-assets), 2019.
