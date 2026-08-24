---
title: "Glossary"
canonical_id: glossary
node_type: source
tags:
  - course-guide
  - orientation
source_files:
  - notes/00-course-guide/01-orientation/glossary.md
status: draft
---
# Glossary

This glossary gives concise working definitions for recurring terms. Complex
mechanisms, legal distinctions, and trade-offs require the fuller explanations
in the related topic notes. Definitions involving law or regulation are general
and can vary by jurisdiction and date.

Entries define a term as it is normally used in this repository. The same
abbreviation can have different meanings in different contexts. In particular,
**RWA** can mean *real-world asset* in tokenization or *risk-weighted assets* in
bank regulation; **DA** can mean *data availability* in blockchain architecture
or *digital asset* informally; and **IM** can mean *initial margin* in markets or
*instant messaging* elsewhere. Always resolve an abbreviation from its section
and surrounding sentence.

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

## Payments, Market Infrastructure, and Trading

| Term or abbreviation | Explanation |
|---|---|
| **ACH (Automated Clearing House)** | A batch-oriented system or network for clearing electronic bank-account payments, especially payroll, bill payments, and direct debits. ACH is a category and, in the United States, is also used for the networks governed by Nacha rules. |
| **API (Application Programming Interface)** | A defined way for software systems to request data or actions from one another. Payment initiation, exchange trading, custody, and blockchain-node services commonly expose APIs. An API is an access layer, not the underlying ledger or legal agreement. |
| **ATS (Alternative Trading System)** | In US securities regulation, a trading venue that matches orders but is regulated differently from a national securities exchange. The broader economic idea includes non-exchange electronic venues and some dark pools. |
| **BIC (Business Identifier Code)** | An ISO 9362 code used to identify financial and non-financial institutions in financial messaging. It is often called a SWIFT code, although SWIFT operates the messaging network and registration infrastructure rather than being the code's legal name. |
| **CCP (Central Counterparty)** | An FMI that becomes buyer to every seller and seller to every buyer through novation or an equivalent legal mechanism. It manages counterparty risk with membership rules, margin, a default fund, and a default waterfall. |
| **CHAPS (Clearing House Automated Payment System)** | The United Kingdom's sterling high-value payment system, operated by the Bank of England as part of its RTGS service. |
| **Clearing member** | A participant that accesses a CCP directly and is responsible to the CCP for its own positions and, where offered, client positions. Clients that are not members clear indirectly through one. |
| **CLS (Continuous Linked Settlement)** | A specialized financial market infrastructure that settles eligible foreign-exchange payment instructions using payment-versus-payment, reducing principal risk between the two currency legs. The company is CLS Group; the core settlement service is commonly called CLSSettlement. |
| **CLOB (Central Limit Order Book)** | An electronic book that ranks buy and sell limit orders, commonly by price and then time, and matches compatible orders under venue rules. |
| **CPMI (Committee on Payments and Market Infrastructures)** | The BIS-hosted international standard-setting committee for payment, clearing, settlement, and related infrastructure. It was formerly called CPSS. |
| **CPSS (Committee on Payment and Settlement Systems)** | The former name of CPMI. Older documents, including the original 2012 PFMI publication, use CPSS-IOSCO. |
| **CSD (Central Securities Depository)** | An FMI that operates the authoritative or central book-entry system for securities, can support issuance and asset servicing, and commonly operates or connects to securities settlement. |
| **DNS (Deferred Net Settlement)** | Settlement in which payment or transfer obligations accumulate, are netted, and settle at specified times rather than individually in real time. It is efficient in liquidity use but creates exposure until settlement. |
| **DvP (Delivery versus Payment)** | A securities-settlement mechanism that links delivery of securities to payment so that one occurs if and only if the other occurs, reducing principal risk. Different DvP models settle gross or net legs. |
| **ETF (Exchange-Traded Fund)** | A pooled investment vehicle whose shares trade on an exchange. Authorized participants normally create or redeem large units against cash or asset baskets, supporting arbitrage between market price and NAV. |
| **FMI (Financial Market Infrastructure)** | A multilateral system used for clearing, settling, or recording payments, securities, derivatives, or other financial transactions. PFMI categories include payment systems, CSDs, securities settlement systems, CCPs, and trade repositories. |
| **FIX (Financial Information eXchange)** | A widely used electronic messaging protocol for orders, executions, allocations, and market data in securities and derivatives markets. |
| **FX (Foreign Exchange)** | Currencies and the market for exchanging them. An FX transaction has two currency legs, which creates settlement principal risk if they do not complete together. |
| **Herstatt risk** | FX settlement risk that one party pays the currency it sold but does not receive the currency it bought because the counterparty fails between the two legs. Named after the 1974 failure of Bankhaus Herstatt. |
| **IBAN (International Bank Account Number)** | A standardized account identifier used in many countries for cross-border and domestic bank payments. It identifies an account under a national structure; it is not itself a payment network. |
| **ICSD (International Central Securities Depository)** | A CSD operating across currencies and markets, particularly for international securities. Euroclear Bank and Clearstream Banking Luxembourg are major examples. |
| **ISO 20022** | An international standard and structured data model for financial messages. It defines business concepts and message schemas; it is not a settlement network or cryptocurrency protocol. |
| **LVPS (Large-Value Payment System)** | A payment system designed mainly for high-value or time-critical payments, typically between financial institutions. Many LVPSs use RTGS. |
| **MMF (Money Market Fund)** | A regulated fund investing in short-duration, high-quality money-market instruments. An MMF share is an investment claim, not a bank deposit, even if the fund seeks a stable NAV. |
| **MTF (Multilateral Trading Facility)** | Under EU/UK market regulation, a multilateral venue operated by an investment firm or market operator that brings together third-party buying and selling interests under non-discretionary rules. |
| **NDF (Non-Deliverable Forward)** | An FX forward settled in a convertible currency for the difference between a contracted rate and a reference rate, without physical delivery of the restricted or non-deliverable currency. |
| **Novation** | Replacement of an existing legal obligation with a new one. In central clearing, novation commonly replaces the original bilateral trade with two trades against the CCP. |
| **OTC (Over the Counter)** | Trading negotiated outside a centralized exchange, often bilaterally or through dealer and electronic networks. OTC can be highly automated and standardized; it does not mean informal or unregulated. |
| **PFMI (Principles for Financial Market Infrastructures)** | The CPMI-IOSCO international standards for systemically important payment systems, CSDs, securities settlement systems, CCPs, and trade repositories. |
| **PvP (Payment versus Payment)** | A settlement mechanism ensuring that the final transfer of one currency occurs if and only if the other currency transfers, reducing FX principal risk. |
| **RFQ (Request for Quote)** | A trading method in which a participant asks one or more dealers or liquidity providers for a firm or indicative price for a specified instrument and size. |
| **RTGS (Real-Time Gross Settlement)** | Continuous settlement of payment instructions individually, in central bank or another settlement asset, without waiting for batch netting. “Real time” refers to processing during operating hours; operational and legal details still determine finality. |
| **SSS (Securities Settlement System)** | Infrastructure that transfers securities by book entry under predefined rules. A CSD often operates an SSS, but the depository and settlement functions are conceptually distinct. |
| **STP (Straight-Through Processing)** | Automated processing from trade or payment initiation through confirmation, clearing, settlement, and reporting without manual re-entry. Exceptions and data mismatches prevent complete STP. |
| **SWIFT (Society for Worldwide Interbank Financial Telecommunication)** | A member-owned cooperative providing secure financial messaging and standards. SWIFT messages instruct institutions; SWIFT generally does not hold customer money or perform the settlement itself. |
| **TARGET Services** | Eurosystem market infrastructures, including T2 for euro RTGS, T2S for securities settlement, and TIPS for instant payments. “TARGET2” refers to the predecessor platform replaced in 2023 by T2. |
| **T2S (TARGET2-Securities)** | The Eurosystem platform that provides harmonized securities settlement in central bank money to participating CSDs. It does not replace the CSD's legal and asset-servicing role. |
| **TIPS (TARGET Instant Payment Settlement)** | The Eurosystem service for settling eligible instant retail payments in central bank money around the clock. |
| **Trade repository (TR)** | An FMI that centrally collects and maintains records of derivatives or other transactions for transparency, regulatory reporting, and risk monitoring. |

### Additional payment and settlement terms

| Term | Explanation |
|---|---|
| **Acquirer / acquiring bank** | Payment provider that contracts with a merchant to accept card or other payments and submits transactions into the relevant network. It is distinct from the cardholder's issuer. |
| **Beneficiary** | Intended recipient of a payment or transfer. The beneficiary customer, beneficiary institution, account holder, and ultimate beneficial owner may be different parties. |
| **Card issuer** | Institution issuing a payment card or account credential to the cardholder, authorizing transactions, billing or debiting the customer, and funding accepted card payments under scheme rules. |
| **Chargeback** | Reversal process under card-scheme or payment rules through which an issuer disputes and returns a transaction to the acquirer, subject to evidence, reason codes, and deadlines. It is not the same as blockchain reversal. |
| **Correspondent banking** | Arrangement in which one bank provides accounts and payment services to another, enabling access to currencies or markets where the respondent lacks direct infrastructure. |
| **Cover payment** | Cross-border payment structure in which the customer instruction travels directly between sending and receiving institutions while a separate interbank cover transfer moves settlement funds through correspondents. |
| **Credit transfer** | Payment initiated by the payer to transfer funds to a beneficiary. It contrasts with a direct debit initiated by the payee under a mandate. |
| **Direct debit** | Payment collected by a payee from a payer's account under prior authorization or mandate, normally with scheme-specific return and consumer-protection rules. |
| **Final settlement** | Irrevocable and unconditional transfer of an asset or discharge of an obligation under the governing system and law. User-interface confirmation can precede final settlement. |
| **Gross settlement** | Settlement of each obligation individually without netting it against other obligations. It reduces accumulated exposure but can require more intraday liquidity. |
| **Interchange fee** | Fee commonly paid by a merchant acquirer to a card issuer under scheme rules. It is one component of the merchant's total payment-acceptance cost. |
| **Intraday credit** | Credit available and repayable within a business day to support payment or securities settlement. It can be collateralized and may be supplied by a central bank or commercial institution. |
| **Nesting** | Correspondent-banking arrangement in which a respondent gives downstream institutions indirect access to its correspondent account, making transparency and risk management more complex. |
| **Netting** | Combining offsetting obligations into smaller net amounts. Payment netting reduces liquidity needs; close-out netting also determines one net claim after default if enforceable. |
| **Nostro account** | From a bank's perspective, “our account with you”: an account it holds at another bank, often in a foreign currency, to make and receive payments. |
| **Originator** | Person or entity initiating a transfer. AML and payment rules may distinguish the originator from the ordering customer, sending institution, or account owner. |
| **Payment instrument** | Tool or procedure a payer uses to initiate payment, such as a card, credit-transfer instruction, direct-debit mandate, check, or tokenized payment credential. |
| **Payment message** | Structured instruction or information exchanged to initiate, route, clear, settle, reconcile, or report a payment. It is not the money itself. |
| **Prefunding** | Placing cash or settlement assets in an account before obligations arise so payments can complete without unsecured intraday credit. It reduces credit exposure but traps liquidity. |
| **Reconciliation** | Comparing independent records and resolving differences so balances, transactions, positions, and lifecycle events agree. Shared ledgers reduce some breaks but do not eliminate offchain and legal reconciliation. |
| **Respondent bank** | Bank receiving correspondent services from another bank, such as access to a currency account or payment network. |
| **Return / reversal / refund** | Different mechanisms for sending value back or undoing customer effect. A return rejects or sends back a payment under scheme rules; reversal cancels or offsets an entry; refund is a new payment initiated by a merchant or payee. |
| **Serial payment** | Cross-border payment in which the customer instruction and settlement value pass through the same chain of correspondent institutions. |
| **Settlement asset** | Asset used to discharge obligations, such as central-bank reserves, commercial-bank money, or a defined token. Its issuer and credit/liquidity quality are central to settlement risk. |
| **Value date** | Date on which funds become effective for interest and settlement purposes. It can differ from instruction, execution, booking, and customer-notification dates. |
| **Vostro account** | From a bank's perspective, “your account with us”: an account it maintains on its books for another bank. One bank's nostro is the other bank's vostro. |

## Instruments, Valuation, and Market Risk

| Term or abbreviation | Explanation |
|---|---|
| **AP (Authorized Participant)** | A financial institution contractually permitted to create and redeem ETF creation units directly with the fund. AP arbitrage helps align ETF market price with underlying value. |
| **APR (Annual Percentage Rate)** | A simple annualized rate that normally does not incorporate intra-year compounding. Product conventions vary, so the rate basis and included fees must be checked. |
| **APY (Annual Percentage Yield)** | An annualized return including assumed compounding. In crypto, displayed APY can combine borrower interest, token incentives, and changing asset prices, so it is not a guaranteed cash yield. |
| **Basis risk** | Risk that a hedge and the exposure it is meant to offset do not move together. It can arise from different instruments, maturities, venues, currencies, reference rates, or settlement terms. |
| **CD (Certificate of Deposit)** | A bank deposit instrument with specified maturity and interest terms. Tradability, deposit-insurance treatment, and early-withdrawal rights vary. |
| **CDS (Credit Default Swap)** | A derivative in which a protection buyer pays a premium and the seller compensates specified credit losses if a defined credit event occurs, subject to contract terms. |
| **Commercial paper (CP)** | Short-term unsecured debt issued by a company or financial institution for working-capital and funding needs. |
| **Convexity** | The curvature in the relationship between a fixed-income instrument's price and yield. It refines duration estimates for larger rate moves and is affected by embedded options. |
| **Duration** | A family of measures for the timing and interest-rate sensitivity of cash flows. Modified duration approximates percentage price change for a small parallel yield move. |
| **EBITDA** | Earnings before interest, taxes, depreciation, and amortization. It is an operating-performance proxy, not cash flow, and definitions can be adjusted by issuers. |
| **ETF creation unit** | A large block of ETF shares that an authorized participant creates or redeems directly with the fund, commonly in exchange for a basket of assets and cash. |
| **EV (Enterprise Value)** | An analytical measure of the value attributed to a company's operations for all capital providers, often approximated as equity value plus debt, preferred equity, and non-controlling interests minus cash. |
| **FDV (Fully Diluted Valuation)** | Token price multiplied by an estimated fully diluted supply. It applies the current marginal price to future or locked units and is not the cash invested or a directly realizable sale value. |
| **Forward** | A bilateral contract obliging parties to transact an asset or settle a price difference at a future date under agreed terms. |
| **Futures contract** | A standardized forward-like contract traded on a venue and normally cleared through a CCP with daily variation margin. |
| **Haircut** | A percentage reduction applied to collateral's market value when determining recognized collateral value. It protects against volatility, liquidation cost, concentration, credit deterioration, and close-out delay. |
| **IM (Initial Margin)** | Collateral intended to cover potential adverse exposure during the period needed to close or replace positions after a counterparty default. |
| **Implementation shortfall (IS)** | Total execution cost relative to the price when an investment decision was made, including executed-price cost, fees, delay, and opportunity cost on unfilled quantity. |
| **IRRBB (Interest Rate Risk in the Banking Book)** | Risk to a bank's earnings or economic value from interest-rate movements affecting non-trading-book assets, liabilities, and off-balance-sheet positions. |
| **LVR (Loss Versus Rebalancing)** | For an AMM LP, the shortfall relative to an idealized continuously rebalanced portfolio caused when better-informed arbitrageurs trade against stale onchain prices. |
| **Mark-to-market (MTM)** | Revaluation of a position using current market prices or valuation inputs. MTM changes can create variation-margin calls before a position is closed. |
| **Notional amount** | Reference amount used to calculate derivative cash flows or exposure. It is not generally the same as market value, amount invested, or counterparty credit exposure. |
| **Option** | A contract giving its buyer a right, but not an obligation, to buy or sell or receive a contingent payoff under specified terms. The seller accepts the corresponding obligation. |
| **Repo (Repurchase Agreement)** | A sale of securities with an agreement to repurchase equivalent securities later. Legally often a sale and repurchase, it is economically similar to collateralized cash borrowing or securities financing. |
| **Securities lending** | Temporary transfer of securities against collateral and a fee, with an obligation to return equivalent securities. Used for short selling, market making, settlement, and financing. |
| **SPV (Special-Purpose Vehicle)** | A legal entity formed for a limited purpose, such as holding assets, issuing securities, or isolating risks. “Bankruptcy remote” is a designed legal property, not a guarantee that the SPV cannot fail. |
| **Swap** | A derivative exchanging defined cash-flow streams, such as fixed versus floating interest or one currency versus another. |
| **TCA (Transaction Cost Analysis)** | Measurement of execution quality using benchmarks such as arrival price, VWAP, spread, impact, and implementation shortfall. |
| **TWAP (Time-Weighted Average Price)** | Average price over time. In trading it is an execution benchmark; in DeFi it often refers to an oracle observation accumulated across a time window. |
| **VaR (Value at Risk)** | A quantile estimate of loss over a chosen horizon and confidence level under a specified model. It does not show the average or maximum loss beyond the threshold. |
| **VM (Variation Margin)** | Collateral exchanged to cover current mark-to-market exposure as prices change. |
| **VWAP (Volume-Weighted Average Price)** | Average traded price weighted by transaction volume. It is used as an execution benchmark and sometimes in reference-price construction. |

### Additional instrument and microstructure terms

| Term | Explanation |
|---|---|
| **Adverse selection** | Risk of trading against someone with better information. Liquidity providers widen spreads or reduce size when incoming flow is more likely to precede an unfavorable price move. |
| **Beneficial ownership** | Economic interest and associated rights held through an intermediary or nominee rather than direct registration on the issuer's authoritative record. Legal meaning varies by jurisdiction. |
| **Call auction** | Trading method that accumulates orders and chooses one clearing price under volume-maximization and tie-break rules. Opening, closing, and volatility auctions concentrate liquidity. |
| **Corporate action** | Issuer or security event affecting holders, such as dividend, split, merger, tender, redemption, conversion, or vote. It requires entitlement, election, tax, and settlement processing. |
| **Dark pool** | Trading venue or mechanism with limited pre-trade transparency, intended partly to reduce information leakage for large orders. It still depends on reference pricing, access, and surveillance. |
| **Effective spread** | Execution-cost measure comparing a trade price with the prevailing midpoint, normally doubled and signed by trade direction. |
| **Iceberg order** | Order displaying only part of its total quantity while keeping reserve size hidden, subject to venue priority and replenishment rules. |
| **Internalization** | Broker-dealer execution of customer flow against its own inventory or other internal flow instead of routing entirely to an external venue. It can improve price while creating conflicts. |
| **Legal title** | Ownership status recognized by applicable property, securities, account, or registry law. Control of a token or private key does not automatically establish title to an offchain asset. |
| **Maker-taker pricing** | Venue fee model charging orders that remove liquidity and rebating or differently charging orders that add liquidity. It influences routing and queue competition. |
| **Market impact** | Price movement associated with executing an order because it consumes liquidity or reveals information. It can contain temporary and persistent components. |
| **Market order** | Instruction prioritizing immediate execution against available liquidity, without guaranteeing the last price or a maximum execution price. |
| **Order book depth** | Quantity available at or near successive bid and ask prices. A tight quoted spread can coexist with little depth. |
| **Post-only order** | Order instruction that should add liquidity and cancel or reprice if it would immediately execute, depending on venue rules. |
| **Prime broker** | Institution providing integrated financing, clearing, custody, securities lending, reporting, and operational services to active investment clients. |
| **Price discovery** | Process through which trading and information produce observable market prices. The venue with most volume is not necessarily the venue leading discovery. |
| **Primary market** | Issuance market in which new securities or fund units are created and capital or assets flow to the issuer or vehicle. |
| **Realized spread** | Liquidity-provider execution measure comparing trade price with a midpoint observed later, after allowing some price discovery to occur. |
| **Secondary market** | Market in which existing instruments trade among investors after issuance. Secondary liquidity can affect financing cost but usually does not directly fund the issuer. |
| **Short selling** | Selling an asset the seller does not own outright, commonly after borrowing it, with an obligation to acquire and return or deliver the asset later. |
| **Stop order** | Order activated when a trigger price is reached, after which it becomes a market or limit instruction under venue rules. The trigger is not a guaranteed execution price. |

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

### Cryptography, data, and execution abbreviations

| Term or abbreviation | Explanation |
|---|---|
| **ABI (Application Binary Interface)** | Rules for encoding typed smart-contract function calls, return values, and events as bytes. In EVM systems, wallets and applications need an ABI to translate between human-readable functions and calldata. |
| **Account abstraction (AA)** | Moving account authorization and fee logic from a fixed protocol account format into programmable accounts. It can enable recovery, session keys, batching, sponsored fees, and alternative signatures. |
| **ACL (Access-Control List)** | A list specifying which identities or roles may perform actions on a resource. Permissioned ledgers, APIs, and enterprise smart contracts frequently use ACLs. |
| **Address checksum** | A representation rule that helps detect typing errors in an address, such as mixed-case EIP-55 Ethereum addresses. A checksum does not prove who controls the address. |
| **AES (Advanced Encryption Standard)** | A widely used symmetric encryption standard. Unlike public-key signatures, AES uses a shared secret key for encryption and decryption. |
| **ASIC (Application-Specific Integrated Circuit)** | Hardware designed for a narrow computational task. Bitcoin mining commonly uses SHA-256 ASICs that are far more efficient than general-purpose processors. |
| **BIP (Bitcoin Improvement Proposal)** | A design document proposing information, processes, standards, or consensus changes for the Bitcoin ecosystem. A BIP is not automatically adopted merely because it is numbered. |
| **BIP-32** | Bitcoin standard for hierarchical deterministic wallets, allowing many child keys to be derived from one root seed. |
| **BIP-39 / BIP39** | Widely used mnemonic-code standard mapping entropy to a human-readable word sequence and deriving a seed. It is common across wallets but is not itself a Bitcoin consensus rule. |
| **BIP-44** | A convention for organizing hierarchical deterministic wallet derivation paths by purpose, asset type, account, change branch, and address index. |
| **BLS signature** | Signature family based on pairing-friendly cryptography that supports efficient aggregation of many signatures. Ethereum consensus uses BLS signatures for validator attestations. |
| **BLS12-381** | A pairing-friendly elliptic curve used in Ethereum consensus and many zero-knowledge systems. It is the curve, not a consensus algorithm. |
| **Bytecode** | Machine-readable instructions executed by a virtual machine. Verified source code is compiled into bytecode, but deployed bytecode is ultimately what consensus executes. |
| **Calldata** | Read-only input bytes supplied to an EVM call. On Ethereum and rollups it also has data-publication cost implications distinct from persistent contract storage. |
| **Content addressing** | Identifying data by a cryptographic digest of its content rather than by a server location. IPFS uses content identifiers in this way. |
| **DAG (Directed Acyclic Graph)** | A graph whose directed edges contain no cycles. DAGs appear in transaction ordering, dependency representation, and some distributed-ledger designs; not every DAG ledger is a blockchain. |
| **DID (Decentralized Identifier)** | A W3C identifier format designed to be resolved to a document describing verification methods and services without depending on one centralized namespace provider. A DID does not itself prove real-world identity. |
| **ECDSA (Elliptic Curve Digital Signature Algorithm)** | Digital-signature algorithm used by Bitcoin and Ethereum for transaction authorization, with different surrounding encoding and hashing rules. |
| **Ed25519** | A widely used digital-signature scheme based on Edwards-curve cryptography. Several blockchains and identity systems use it; it is not compatible with Ethereum's ordinary ECDSA account signatures. |
| **EIP (Ethereum Improvement Proposal)** | A document proposing an Ethereum standard, core-protocol change, networking rule, interface, or process. Core EIPs require ecosystem coordination to activate. |
| **EOA (Externally Owned Account)** | Ethereum term for an account controlled directly by a private key under protocol-defined signature and nonce rules, as distinct from a contract account. Account abstraction blurs this user-facing distinction. |
| **ERC (Ethereum Request for Comments)** | An EIP category defining application-level standards such as token and account interfaces. “ERC” does not imply the implementation is secure or legally compliant. |
| **ERC-20** | Standard interface for fungible Ethereum tokens, including balances, transfers, allowances, and related events. Implementations can add minting, fees, freezing, rebasing, or upgrades. |
| **ERC-721** | Standard interface for non-fungible tokens with unique token identifiers, ownership, transfer, and approvals. It does not define intellectual-property or offchain-asset rights. |
| **ERC-1155** | Multi-token standard supporting fungible, non-fungible, and semi-fungible token IDs in one contract with batch operations. |
| **ERC-4626** | Standard interface for tokenized vault shares and conversions between shares and underlying assets. It standardizes accounting calls but does not eliminate strategy, liquidity, or rounding risk. |
| **ERC-4337** | Higher-layer Ethereum account-abstraction design using UserOperations, bundlers, a shared EntryPoint contract, and optional paymasters without a consensus-layer change. |
| **EIP-1559** | Ethereum fee-market change introducing a protocol-calculated base fee that is burned, variable block capacity around a target, and separate priority fees. |
| **EIP-4844 / Proto-danksharding** | Ethereum upgrade introducing blob-carrying transactions and a separate data-fee market to provide temporary, cheaper data availability for rollups. |
| **EIP-712** | Standard for typed structured-data signing so wallets can display domains and fields more intelligibly than opaque bytes. Safe use still requires correct domain separation and user comprehension. |
| **EIP-7702** | Ethereum transaction capability allowing an EOA to set executable delegation code, enabling account-like programmability while retaining the account address. |
| **EVM (Ethereum Virtual Machine)** | Ethereum's deterministic execution environment, a 256-bit stack machine that runs contract bytecode and meters resources with gas. Several other chains implement EVM compatibility. |
| **FIPS (Federal Information Processing Standards)** | US government standards for information technology and cryptographic modules. “FIPS validated” applies to a defined module and configuration, not automatically an entire custody product. |
| **Function selector** | In the EVM ABI, the first four bytes of the Keccak-256 hash of a canonical function signature. Selectors can collide, so context and dispatch logic matter. |
| **HD wallet (Hierarchical Deterministic wallet)** | A wallet deriving many keys and addresses from one seed according to a tree structure, commonly using BIP-32-related conventions. |
| **HMAC (Hash-Based Message Authentication Code)** | A construction combining a cryptographic hash with a secret key to authenticate data. It establishes integrity and shared-key authenticity, not public verifiability. |
| **HSM (Hardware Security Module)** | Tamper-resistant hardware designed to generate, store, and use cryptographic keys under controlled policies. An HSM reduces raw-key exposure but still depends on configuration, authorization, backup, and operations. |
| **IPFS (InterPlanetary File System)** | A peer-to-peer content-addressed data system commonly used for NFT metadata and application assets. An IPFS content identifier verifies content, but persistence still requires nodes to retain or pin it. |
| **JSON-RPC** | Remote-procedure-call convention using JSON requests and responses. Ethereum nodes commonly expose JSON-RPC methods for state queries, transaction submission, logs, and simulation. |
| **Keccak-256** | Hash function used by Ethereum for addresses, storage, transaction structures, and the EVM `KECCAK256` opcode. Ethereum's Keccak-256 differs in padding from standardized SHA3-256. |
| **KMS (Key Management Service/System)** | Software or managed infrastructure for creating, storing, rotating, and authorizing use of encryption or signing keys. It may rely on HSMs but is a broader operational control plane. |
| **KZG commitment** | Polynomial commitment scheme used for Ethereum blob data. It lets a verifier check evaluations against a compact commitment and relies on a structured reference setup. |
| **Mempool** | A node's local collection of valid but unconfirmed transactions. There is no single universal mempool; policies, timing, private order flow, and network topology create different views. |
| **Merkle proof** | Compact proof that data is included in, or excluded from, an authenticated tree committed by a root hash. The proof establishes relation to the root, not the truth of the data's external meaning. |
| **Multisig (Multi-signature wallet)** | Contract or script requiring a threshold of several keys to authorize an action, such as 2 of 3. It reduces single-key risk but adds signer, coordination, upgrade, and recovery risks. |
| **Nonce** | A value used once or in sequence. Account blockchains use transaction nonces to order actions and prevent replay; PoW mining varies a nonce while searching for a valid hash. The meanings are related but not identical. |
| **P2P (Peer to Peer)** | Network architecture in which nodes communicate directly under a protocol rather than exclusively through a central server. Peer discovery and topology still create concentration and eclipse risk. |
| **PKI (Public Key Infrastructure)** | Governance, certificates, authorities, and procedures that bind public keys to identities or roles. Permissioned networks commonly use PKI for membership. |
| **Precompile** | A protocol-provided function exposed at a special address to perform operations more efficiently than ordinary VM bytecode, often cryptography. |
| **RPC (Remote Procedure Call)** | An interface through which software requests operations from another process, such as querying a blockchain node. Unless responses are proof-verified, an RPC client trusts the provider's view. |
| **RLP (Recursive Length Prefix)** | Ethereum encoding used for several execution-layer data structures. It encodes nested byte strings and lists; newer consensus data commonly uses SSZ instead. |
| **SDK (Software Development Kit)** | Libraries, tools, examples, and interfaces supplied to help developers integrate with a platform. Using an SDK adds a software-supply-chain and version dependency. |
| **Seed phrase / mnemonic** | Human-readable words used to back up wallet seed material, often under BIP-39. Anyone obtaining the phrase can usually derive and control the wallet's keys. |
| **SHA-256 / SHA256** | Cryptographic hash standardized by NIST and used extensively by Bitcoin, including in proof of work and block/transaction identifiers. |
| **SSZ (Simple Serialize)** | Serialization and Merkleization format used by Ethereum's consensus layer. It provides deterministic encoding and commitment structures for consensus objects. |
| **TSS (Threshold Signature Scheme)** | Cryptographic protocol in which several parties jointly produce one valid signature without reconstructing the complete signing key in one place. MPC custody often uses a TSS. |
| **UTXO (Unspent Transaction Output)** | A discrete spendable output created by a prior transaction and not yet consumed. Bitcoin state is modeled as the set of valid UTXOs rather than mutable account balances. |
| **VC (Verifiable Credential)** | W3C data model for issuer-signed claims that a holder can present and a verifier can check. A valid signature does not ensure the issuer's claim is factually correct. |
| **VM (Virtual Machine)** | Abstract execution environment defining instructions, memory, calls, state access, resource metering, and error behavior for programs. |
| **VRF (Verifiable Random Function)** | Cryptographic function producing pseudorandom output with a proof that anyone can verify against a public key. Availability and input-selection assumptions still affect applications. |
| **WASM (WebAssembly)** | Portable bytecode and execution format used in browsers and some blockchains or smart-contract environments. Different WASM-based chains expose different host functions and metering. |
| **Web3** | Broad, non-standardized label for blockchain-based applications, digital ownership, wallets, and decentralized protocols. Its meaning depends on context and should not replace an architectural description. |
| **ZKP (Zero-Knowledge Proof)** | Proof that a statement is true without revealing more than required about the witness. “Zero knowledge” concerns information leakage; succinctness and computational integrity are separate properties. |
| **zk-SNARK** | Succinct non-interactive zero-knowledge argument, usually compact and fast to verify. Some constructions require a trusted or structured setup. |
| **zk-STARK** | Scalable transparent argument of knowledge using hash-based techniques and no trusted setup in the conventional sense, typically with larger proofs than many SNARKs. |

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

### Consensus, scaling, and modular architecture

| Term or abbreviation | Explanation |
|---|---|
| **ABCI (Application Blockchain Interface)** | Interface separating Tendermint/CometBFT consensus and networking from the application state machine. Cosmos SDK applications communicate with consensus through ABCI or its successors. |
| **Appchain (Application-specific blockchain)** | A blockchain customized for one application or ecosystem rather than sharing one general-purpose execution environment. It gains sovereignty and tailored resources but must arrange security, interoperability, and liquidity. |
| **Attestation** | A validator's signed statement about a block, checkpoint, availability sample, or other consensus fact. In Ethereum PoS, attestations contribute to fork choice and finality. |
| **BABE (Blind Assignment for Blockchain Extension)** | Polkadot block-production protocol using verifiable randomness to assign block-production slots. It operates with GRANDPA finality. |
| **Blob** | In Ethereum, a large temporary data object carried by an EIP-4844 blob transaction and committed cryptographically. Rollups use blobs to publish data without placing it permanently in EVM calldata. |
| **Block proposer / producer** | Participant selected or winning the right to construct and publish a candidate block. Proposal authority does not permit invalid state transitions to pass honest validation. |
| **Checkpoint** | Designated block or state used in finality, synchronization, or trust anchoring. Its exact security meaning is protocol-specific. |
| **CometBFT** | Successor implementation of Tendermint Core, providing BFT consensus and networking for replicated applications, including many Cosmos SDK chains. |
| **DA (Data Availability)** | Assurance that the transaction data needed to verify state transitions or recover state is accessible. A hash commitment proves integrity but not availability. |
| **DAC (Data Availability Committee)** | A designated committee attesting that it stores or can provide transaction data, used by some validiums or permissioned rollup modes. It is cheaper than full L1 publication but adds committee trust. |
| **Data availability sampling (DAS)** | Technique allowing nodes to sample coded data and obtain high confidence that an entire block is available without downloading all of it. |
| **Danksharding** | Ethereum roadmap design in which a shared market supplies large data capacity for rollups, with proposer-builder separation and data-availability sampling. Proto-danksharding is the earlier blob stage, not full danksharding. |
| **Economic finality** | Finality backed by detectable rule violations and economic penalties, such as slashing a material portion of stake. It does not guarantee that application logic or external data were correct. |
| **EL / CL (Execution Layer / Consensus Layer)** | Ethereum's post-Merge architecture separates transaction execution and state from PoS consensus. Execution and consensus clients communicate through the Engine API. |
| **Engine API** | Authenticated interface connecting an Ethereum execution client and consensus client so consensus can request and validate execution payloads. |
| **Finality gadget** | Protocol layered with a block-production or fork-choice mechanism to finalize checkpoints, such as GRANDPA or Casper FFG. |
| **FFG (Friendly Finality Gadget)** | Casper finality mechanism used in Ethereum's Gasper design. Validators vote on checkpoint links to justify and finalize checkpoints. |
| **Fraud proof / fault proof** | Evidence that an asserted state transition was invalid, used by optimistic rollups during a dispute window. Security requires data availability and at least one able honest challenger under the protocol assumptions. |
| **Fork choice** | Rule for selecting the current canonical head among valid competing branches. It is distinct from the rule that finalizes older history. |
| **Gasper** | Ethereum PoS consensus design combining LMD-GHOST fork choice with Casper FFG finality. |
| **GHOST (Greedy Heaviest-Observed Sub-Tree)** | Fork-choice family that selects branches using observed weight across a block tree rather than only the tip. Ethereum uses an LMD-GHOST variant. |
| **GRANDPA** | Polkadot's finality gadget, which finalizes chains of blocks independently of BABE block production. |
| **L0 / Layer 0** | Informal label for an interoperability, shared-security, or blockchain-building layer below application chains, such as a relay or hub architecture. It is not a standardized technical category. |
| **L1 / Layer 1** | Base blockchain providing native consensus and settlement, such as Bitcoin, Ethereum, Solana, or an appchain's sovereign base layer. |
| **L2 / Layer 2** | System executing transactions outside an L1 while deriving a defined security or settlement property from that L1. Rollups are the principal example; a sidechain is not automatically an L2. |
| **L3 / Layer 3** | Informal term for an application-specific or recursively layered system built above an L2. Its data, settlement, and bridging assumptions must be specified rather than inferred from the label. |
| **Light client** | Client that verifies headers, consensus evidence, and selected proofs without executing and storing the complete chain. Assurance depends on the protocol's light-client design and data assumptions. |
| **LMD-GHOST (Latest Message Driven GHOST)** | Ethereum fork-choice rule using each validator's latest valid attestation to weight branches. |
| **Long-range attack** | PoS attack constructing an alternative history far in the past, potentially using keys of validators that have already exited and withdrawn. Recent trusted checkpoints or weak subjectivity address this risk. |
| **Optimistic rollup** | Rollup that treats posted state commitments as valid unless successfully challenged during a dispute period. It relies on L1 data availability, correct fault proofs, and honest-challenger availability. |
| **PBS (Proposer-Builder Separation)** | Separation between selecting a block and constructing its ordered transaction payload. It can specialize block building and mitigate some MEV pressures while adding builder and relay concentration risks. |
| **Proposer** | Consensus participant selected to publish a block or block header in a slot or round. |
| **Prover** | System or actor generating a validity proof for execution, commonly in ZK rollups. Prover centralization can affect liveness and censorship even when proof verification is decentralized. |
| **Reorganization / reorg** | Replacement of a recent canonical chain suffix by another valid branch. Applications must reverse provisional events and delay irreversible external actions appropriately. |
| **Rollup** | Scaling system that executes transactions away from an L1 and posts transaction data or commitments plus a validity or fault mechanism to the L1. Exact withdrawal, upgrade, sequencer, and data assumptions vary. |
| **Sequencer** | Actor or mechanism ordering transactions for a rollup or L2. A centralized sequencer can improve speed but creates censorship and availability risk until decentralized or forced-inclusion paths operate. |
| **Sidechain** | Separate blockchain connected by a bridge and secured by its own validators or consensus. Its security does not automatically inherit from the connected L1. |
| **Sovereign rollup** | Rollup whose nodes determine the canonical execution state using their own fork-choice rules over data published to a DA layer, rather than relying on a settlement-layer smart contract to adjudicate state. |
| **State channel** | Protocol in which participants lock state onchain, exchange signed updates offchain, and use the chain for opening, dispute, or closing. Best suited to repeated interactions among known participants. |
| **State root** | Cryptographic commitment to blockchain state at a specific block. It enables proofs about included state but does not make the data available by itself. |
| **TPS (Transactions Per Second)** | Throughput metric. TPS comparisons are meaningful only with transaction complexity, finality, hardware, batching, data publication, and measurement method specified. |
| **Validium** | Validity-proof scaling design keeping transaction data off the settlement L1, often with a DAC. Proofs protect computation integrity; offchain availability remains an added trust assumption. |
| **Validity proof** | Cryptographic proof that a batch's state transition follows the specified program. It protects computational correctness but needs appropriate data availability and verifier correctness. |
| **Volition** | Scaling design allowing users or applications to choose between onchain rollup data availability and offchain validium-like availability. |
| **Weak subjectivity** | PoS property under which a new or long-offline node needs a sufficiently recent trusted checkpoint, then can verify forward objectively. It addresses long-range histories signed by exited validators. |
| **ZK rollup** | Rollup using validity proofs to establish correct batch execution. “ZK” in this label may emphasize proof technology even when transaction privacy is not provided. |
| **zkEVM** | Proof system and execution environment designed to prove EVM-compatible or Ethereum-equivalent execution. Compatibility levels differ across opcode, bytecode, state, and tooling behavior. |

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

### Token, network, and product abbreviations

| Term or abbreviation | Explanation |
|---|---|
| **BTC** | Native asset and unit of account of the Bitcoin network. Bitcoin is the protocol/network; BTC is the asset ticker. |
| **ETH** | Native asset of Ethereum, used for transaction fees, validator staking, and onchain collateral. “Ethereum” refers to the network and protocol, not the asset ticker. |
| **SOL** | Native asset of the Solana network, used for fees and staking. |
| **XRP** | Native asset of the XRP Ledger. XRP is not an issued claim on the company Ripple, although Ripple is an important ecosystem participant and holder. |
| **BNB** | Native asset used across the BNB Chain ecosystem and associated products. Its historical and governance relationship to Binance should be analyzed separately from protocol functionality. |
| **DAI** | Crypto-collateralized dollar-targeting stablecoin created by MakerDAO/Sky protocol mechanisms. Its backing and governance evolved over time and includes both crypto and real-world-asset exposure. |
| **USDS** | Sky ecosystem's newer dollar-targeting stablecoin, convertible with DAI under protocol rules and subject to Sky governance and product-specific controls. |
| **USDC** | USD Coin, a fiat-backed stablecoin issued by Circle under applicable issuer terms. It is a private issuer liability, not US central bank money. |
| **USDT** | Tether USD₮, a fiat-backed stablecoin issued within the Tether group under its terms. Ticker reuse on unofficial contracts makes contract-address verification essential. |
| **PYUSD** | PayPal USD, a US dollar stablecoin issued by Paxos Trust Company for the PayPal ecosystem and external blockchain use. |
| **EURC** | Circle-issued euro-denominated stablecoin. It is a private e-money-like issuer claim under applicable terms, not a digital euro CBDC. |
| **GHO** | Aave ecosystem's overcollateralized dollar-targeting stablecoin, minted through approved facilitator mechanisms governed by Aave. |
| **LUSD** | Liquity protocol's dollar-targeting stablecoin minted against protocol collateral under Liquity's rules. Version-specific design differences matter. |
| **BOLD** | Stablecoin of Liquity V2, with borrower-selected interest and protocol-specific collateral markets. It is distinct from LUSD. |
| **WETH (Wrapped Ether)** | ERC-20 token issued by a same-chain wrapper contract against deposited native ETH. It exists because native ETH does not itself implement ERC-20 functions. |
| **WBTC (Wrapped Bitcoin)** | Tokenized representation of bitcoin on other chains under a custodial minting and redemption structure. It adds custodian, merchant, governance, legal, and smart-contract risk. |
| **NFT (Non-Fungible Token)** | Token with a distinct identifier or position rather than universally interchangeable units. The token does not automatically convey copyright, physical ownership, or legal title. |
| **SBT (Soulbound Token)** | Informal term for a non-transferable or tightly transferable token intended to represent reputation, membership, or credentials. It is a design concept, not one universal standard. |
| **LST (Liquid Staking Token)** | Transferable token representing staked assets and associated reward/slashing economics, such as staked-ETH claims. It adds issuer/protocol, validator, liquidity, and redemption risk. |
| **LRT (Liquid Restaking Token)** | Token representing a restaked position exposed to additional services or slashing conditions beyond base-layer staking. |
| **LP token** | Token or NFT representing a liquidity-provider position in an AMM or pool. Its value depends on reserve composition, fees, range, losses, and redemption rules. |
| **PT (Principal Token)** | In yield-splitting protocols, a claim to principal at maturity, separated from the future yield of an underlying yield-bearing asset. |
| **YT (Yield Token)** | In yield-splitting protocols, a claim to yield generated by an underlying asset until a defined maturity, typically decaying as maturity approaches. |
| **Receipt token** | Token representing a deposit, loan supply position, vault share, bridge claim, or other underlying position. Its unit and redemption accounting must be examined. |
| **Rebasing token** | Token whose displayed balances or total supply adjust according to a rule, rather than accruing value only through a changing market price or share exchange rate. |

## Stablecoins, CBDCs, and Digital Money Forms

| Term | Explanation |
|---|---|
| **Stablecoin** | A token designed to keep a stable value relative to a reference asset, usually `1 token = 1 USD`. A fiat-backed stablecoin normally works like this: users send dollars to an issuer, the issuer holds reserves, mints tokens, and later redeems tokens for dollars. The stablecoin is only as reliable as its reserves, redemption process, legal structure, issuer, and market confidence. |
| **Fiat-backed stablecoin** | A stablecoin backed by cash, bank deposits, Treasury bills, or similar assets. Example flow: deposit $100 with issuer -> issuer mints 100 tokens -> tokens circulate on-chain -> holder redeems 100 tokens -> issuer pays $100 and burns tokens. Main risks: reserve quality, issuer solvency, redemption delays, regulation, bank exposure. |
| **Crypto-collateralized stablecoin** | A stablecoin backed by crypto collateral locked in smart contracts, usually overcollateralized because crypto prices are volatile. Example: lock $150 of ETH to mint/borrow $100 of stablecoin. Main risks: collateral crashes, oracle failure, liquidation failure, governance risk. |
| **Algorithmic stablecoin** | A stablecoin that tries to maintain a peg mainly through incentives, supply changes, or linked tokens rather than full external reserves. These designs are fragile because confidence can collapse if the mechanism cannot absorb redemptions or selling pressure. |
| **Payment stablecoin** | A stablecoin designed primarily for payments and transfers rather than investment. It should maintain stable value, be redeemable, and have reliable reserves. Exact legal meaning depends on jurisdiction and date. |
| **CBDC (Central Bank Digital Currency)** | Digital money issued directly by a central bank. A CBDC is a direct central bank liability, unlike a stablecoin, which is usually a private issuer liability, or a bank deposit, which is a commercial bank liability. |
| **e-CNY (Electronic Chinese yuan / digital renminbi)** | China's retail CBDC issued by the People's Bank of China, with authorized operators providing exchange and circulation services. It is central-bank money and must not be confused with a yuan-referencing private stablecoin. “CNY” is the ISO currency code for the renminbi; “RMB” is the currency's common abbreviation. |
| **Retail CBDC** | A CBDC available to households and businesses. It could function like digital cash, but raises policy questions around privacy, bank deposit outflows, payment competition, and state control. |
| **Wholesale CBDC** | A CBDC available only to banks or financial institutions, mainly for interbank settlement or settlement of tokenized assets. It is less visible to consumers but important for institutional market infrastructure. |
| **Tokenized deposit** | A bank deposit represented as a token. The holder still has a claim on the commercial bank, similar to a normal deposit, but transfer and settlement may happen on shared ledger infrastructure. Difference from stablecoin: a tokenized deposit is bank money; a stablecoin is usually non-bank private issuer money. |
| **Singleness of money** | The principle that different safe forms of the same currency should trade at par: $1 in cash, $1 in a bank deposit, and $1 in a well-functioning stable money instrument should be worth $1. Breaks in singleness show up as de-pegs, discounts, or loss of confidence. |
| **Redemption** | Exchanging a token or claim back for the underlying asset or money. For stablecoins, redemption means returning tokens to the issuer and receiving fiat money. Redemption rights and practical access matter more than the headline peg. |
| **Reserve backing** | Assets held to support redemption of issued money-like claims. For stablecoins, high-quality liquid reserves make it easier to meet redemptions. Poor, risky, opaque, or illiquid reserves make a run more dangerous. |

### Stablecoin and digital-money abbreviations

| Term or abbreviation | Explanation |
|---|---|
| **ART (Asset-Referenced Token)** | MiCA category for a cryptoasset that purports to maintain stable value by referencing another value or right, or a combination, including one or more official currencies. It is distinct from an EMT referencing one official currency. |
| **CDP (Collateralized Debt Position)** | Onchain position that locks collateral and creates or borrows a protocol liability, commonly a stablecoin. Maker originally popularized the term; newer designs may use “vault.” |
| **EMT (E-Money Token)** | MiCA category for a cryptoasset that purports to maintain stable value by referencing one official currency. It is subject to rules linked to electronic money and MiCA. |
| **GENIUS Act** | US *Guiding and Establishing National Innovation for U.S. Stablecoins Act*, enacted in 2025 as Public Law 119-27. It establishes a federal framework for permitted payment-stablecoin issuers, reserves, redemption, supervision, and related requirements. |
| **PAXG** | Pax Gold, a token issued by Paxos representing contractual rights linked to allocated physical gold under the product terms. It is a commodity-backed token, not a stablecoin against fiat. |
| **PSM (Peg Stability Module)** | Smart-contract mechanism that exchanges a protocol stablecoin against an approved reference stablecoin at configured fees and limits, supporting peg liquidity while importing the reference asset's risks. |
| **Seigniorage** | Economic value arising from issuing money at a cost below the value received for it. For stablecoins it can include reserve income net of operating, distribution, and risk costs. |
| **Stablecoin attestation** | Periodic practitioner report on specified reserve information under an attestation standard. It is narrower than a full financial-statement audit and does not by itself prove complete solvency at all times. |
| **Wholesale settlement token** | Digitally represented settlement asset restricted mainly to financial institutions. It may be central bank money, commercial-bank money, or another private liability; “wholesale” describes access and use, not issuer type. |

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
| **MEV (Maximal Extractable Value)** | Value extracted by controlling or influencing transaction ordering within a block. Example: a bot sees a large DEX trade, buys before it, lets the user's trade move the price, then sells after it. This is called a sandwich attack. |
| **TVL (Total Value Locked)** | The dollar value of assets deposited in a DeFi protocol. It is a rough size metric, similar in spirit to AUM, but can be inflated, double-counted, or misleading. |
| **DAO (Decentralized Autonomous Organization)** | A governance structure where rules, treasury decisions, or protocol changes are managed through code and token-holder voting. In practice, DAOs often still depend on core teams, legal wrappers, delegates, and off-chain coordination. |

### DeFi lending, trading, staking, and governance

| Term or abbreviation | Explanation |
|---|---|
| **ADL (Auto-Deleveraging)** | Derivatives-venue mechanism that reduces profitable counterparties' positions when an insolvent account cannot be closed without exceeding available insurance or backstop resources. |
| **AMM invariant** | Mathematical relationship a pool is designed to maintain across reserve changes, such as `x × y = k`. Fees, hooks, concentrated ranges, and accounting modify the simple form. |
| **Borrow cap** | Maximum debt allowed for an asset or market. It limits exposure and can reduce contagion from weak collateral or illiquid debt assets. |
| **Borrow index** | Accumulating factor used to calculate current debt from a scaled balance without updating every borrower continuously. |
| **CLMM (Concentrated-Liquidity Market Maker)** | AMM allowing liquidity providers to allocate capital to chosen price ranges. It increases capital efficiency near the active price but adds range and rebalancing risk. |
| **Close factor** | Maximum portion of an unhealthy borrower's debt that one liquidation action may repay. It controls liquidation size and borrower impact. |
| **Composability** | Ability of protocols and tokens to interact and be reused, often atomically. Technical interface compatibility does not guarantee compatible economics or risk. |
| **Curve / invariant** | Formula translating AMM reserves and trade size into prices and outputs. “Bonding curve” can also refer more broadly to algorithmic token issuance or pricing. |
| **Dutch auction** | Auction in which the offered price becomes progressively more attractive until a bidder accepts. DeFi protocols use variants for collateral liquidation and recapitalization. |
| **eMode (Efficiency Mode)** | Aave risk mode providing higher capital efficiency for assets categorized as strongly correlated, with category-specific LTV and liquidation settings. Correlation can break during stress. |
| **Flash loan** | Loan that must be borrowed and repaid within one atomic transaction or the entire transaction reverts. It provides temporary capital but does not itself cause an exploit; it scales vulnerabilities that assume capital is scarce. |
| **Funding rate** | Periodic payment between long and short perpetual-derivative positions intended to keep the contract price near an index. It is usually exchanged between traders rather than being the same as an exchange fee. |
| **Gauge** | Governance-directed mechanism allocating token incentives among liquidity pools or markets, especially in vote-escrow systems. |
| **Health factor (HF)** | Ratio comparing risk-adjusted collateral with debt in a lending protocol. A value below the protocol threshold—commonly 1—makes a position eligible for liquidation. Formula details vary. |
| **Hook** | Contract or callback extending a protocol at defined lifecycle points. Uniswap v4 hooks can customize fees, liquidity, swaps, or accounting and therefore add independent code and governance risk. |
| **Impermanent loss (IL)** | AMM LP shortfall relative to holding the original assets caused by automatic inventory rebalancing as relative prices change. “Impermanent” does not mean economically unrealized or harmless. |
| **Insurance fund** | Venue or protocol reserve intended to absorb losses from bankrupt positions, liquidation shortfalls, or specified incidents. Coverage rules and sufficiency must be assessed. |
| **Intent** | User-signed statement of desired outcome and constraints without prescribing the exact execution path. Solvers compete or coordinate to fulfill it. |
| **IRM (Interest-Rate Model)** | Lending-protocol formula mapping utilization or other state to borrower and supplier rates. A kinked IRM raises rates sharply beyond target utilization. |
| **Keeper** | External actor or automation service that submits transactions when contract conditions require action, such as liquidation, rebalancing, or expiry. Contracts do not wake themselves. |
| **Liquidation bonus / incentive** | Extra collateral value a liquidator receives relative to debt repaid. It must compensate execution and risk but can increase borrower loss and selling pressure. |
| **LLTV (Liquidation Loan-to-Value)** | Morpho and related term for the debt-to-collateral threshold at which a position can be liquidated. It should not be confused automatically with initial borrowing LTV. |
| **LTV (Loan-to-Value)** | Debt value divided by collateral value, or a closely related borrowing-capacity parameter. Protocols use the term differently, so the mathematical rule must be checked. |
| **MEV-Boost** | Ethereum middleware implementing an out-of-protocol proposer-builder marketplace using relays, allowing validators to choose builder bids instead of constructing all payloads locally. |
| **Oracle Extractable Value (OEV)** | MEV associated with anticipated oracle updates, such as capturing liquidation or arbitrage value created when a price report changes onchain state. |
| **Perpetual / perp** | Derivative resembling a futures contract without a fixed expiry, commonly using funding payments and margin to track an index price. |
| **Protocol-owned liquidity (POL)** | Liquidity positions owned or controlled by a protocol treasury rather than rented solely through short-term user incentives. It still bears LP and token risk. |
| **Rehypothecation** | Reuse by an intermediary or protocol of assets received as collateral. It improves capital efficiency while creating chains of claims and dependency on returning equivalent assets. |
| **Reserve factor** | Portion of lending interest directed to a protocol reserve or treasury rather than suppliers. It can build a loss buffer or fund operations. |
| **Sandwich attack** | Transaction-ordering strategy that trades before and after a victim's price-sensitive transaction, worsening the victim's execution up to its constraints and capturing part of the price impact. |
| **Scaled balance** | Stored principal-like balance multiplied by a global interest index to calculate the current claim or debt. It avoids updating every account each block. |
| **Slippage** | Difference between expected and realized execution, or the permitted output tolerance in a transaction. Slippage can arise from price impact, state changes, latency, and MEV. |
| **Solver** | Actor that finds and submits an execution satisfying a user's intent or batch constraints, potentially routing across venues and using private liquidity. |
| **Supply cap** | Maximum amount of an asset that can be supplied to a lending or collateral market, limiting concentration and exposure. |
| **Utilization** | Share of a lending pool's assets currently borrowed. High utilization can increase rates and simultaneously reduce withdrawal liquidity. |
| **Vault** | Smart contract pooling or managing assets and issuing shares or internal claims. A vault can be passive custody, an ERC-4626 wrapper, or an active strategy; the label alone does not define risk. |
| **Vote escrow (ve-token model)** | Governance model in which users lock tokens for time-weighted voting power, often directing emissions. It encourages commitment but creates delegate, bribery, and liquidity trade-offs. |
| **Wrong-way risk** | Exposure that increases as a counterparty or collateral becomes less creditworthy. Example: a protocol backstop token falling precisely when protocol losses need to be absorbed. |

## Blockchain Analytics and Data Engineering

| Term or abbreviation | Explanation |
|---|---|
| **Address attribution** | Linking a blockchain address to an entity, service, actor category, or event using evidence. Attribution is probabilistic and time-dependent unless confirmed by authoritative records. |
| **Address clustering** | Grouping addresses inferred to share control or operational ownership using transaction heuristics, service data, or other evidence. A cluster is an analytical model, not consensus truth. |
| **Change-address heuristic** | UTXO heuristic inferring which transaction output returns change to the spender. Wallet behavior, batching, CoinJoin, and script choices can produce errors. |
| **Common-input-ownership heuristic** | Inference that inputs spent together in a UTXO transaction are controlled by one entity because their signatures were coordinated. CoinJoin and collaborative transactions are important exceptions. |
| **Direct exposure** | Value transferred directly between the subject and an attributed source or destination. Product methodologies differ on whether smart contracts or intermediaries break directness. |
| **DWH (Data Warehouse)** | Central analytical store combining normalized and historical data for querying, reporting, and modeling. In blockchain analytics it commonly holds blocks, decoded events, prices, labels, and derived exposures. |
| **Entity** | Analytical representation of a person, organization, service, protocol, or actor controlling or using one or more addresses. An entity label can be wrong or incomplete. |
| **ETL (Extract, Transform, Load)** | Data pipeline that extracts source data, transforms and validates it, and loads it into an analytical store. Some architectures use ELT, loading before transformation. |
| **Exposure** | Measured connection between an address/entity and a risk category or counterparty. It can mean direct transfer, multi-hop flow, balance provenance, or another vendor-specific model. |
| **FIFO / LIFO (First In, First Out / Last In, First Out)** | Competing rules for allocating outgoing value to earlier inflows when tracing fungible funds. Blockchain consensus does not specify either rule for account balances. |
| **Graph analytics** | Analysis of addresses or entities as vertices and transfers or relationships as edges, using paths, centrality, community detection, flow, and temporal features. |
| **Heuristic** | Practical inference rule that is useful but not mathematically certain, such as change detection or common-input ownership. Results require confidence, exceptions, and corroboration. |
| **Hop** | One transfer edge in a transaction graph. “Three hops away” does not by itself quantify value, control, intent, or legal risk. |
| **Indirect exposure** | Connection through one or more intermediate transfers. Risk significance generally declines or changes with value, intervening services, time, and methodology rather than hop count alone. |
| **Indexer** | System that extracts chain data, decodes application semantics, handles reorganizations, and stores queryable derived entities. Its database is not itself consensus state. |
| **Peel chain** | Transaction pattern repeatedly sending part of a balance onward while returning change, creating a chain of gradually “peeled” outputs. It can reflect ordinary wallet operations or concealment. |
| **Rescreening** | Re-evaluating historic or current addresses and transactions when attribution, sanctions lists, typologies, or risk rules change. |
| **Taint analysis** | Family of methods tracing association of fungible value with a source. Poison, haircut, FIFO, and proportional models produce different results and should not be treated as legal truth. |
| **Typology** | Recurrent behavioral pattern associated with a financial-crime method, such as ransomware cash-out or layering. A typology is a detection model, not proof that every matching transaction is illicit. |

## Regulation and Classification

| Term | Explanation |
|---|---|
| **SEC** | US Securities and Exchange Commission. Regulates securities markets, investment products, disclosures, and many intermediaries. Crypto disputes often involve whether a token or product is a security. |
| **CFTC** | US Commodity Futures Trading Commission. Regulates derivatives markets and has authority over commodity derivatives and certain anti-fraud/anti-manipulation matters in commodity spot markets. |
| **Howey test** | US legal test for whether something is an investment contract, and therefore a security. In simplified form: investment of money, in a common enterprise, with expectation of profit, mainly from others' efforts. It is often applied to token sales. |
| **Security token** | A token representing a security-like legal claim, such as equity, debt, revenue share, or fund interest. It must usually follow securities laws even if issued on a blockchain. |
| **Commodity** | A broad category of tradable goods or assets. In crypto, BTC is commonly treated as a commodity in the US regulatory context, but classification can depend on asset, facts, jurisdiction, and date. |
| **Travel Rule** | AML rule requiring certain financial institutions and crypto asset service providers to transmit originator and beneficiary information for qualifying transfers. Exact thresholds and implementation vary by jurisdiction. |

### AML, sanctions, and financial-crime terminology

| Term or abbreviation | Explanation |
|---|---|
| **AML/CFT or AML/CFT/CPF** | Anti-Money Laundering and Countering the Financing of Terrorism; the longer form adds Counter-Proliferation Financing. These frameworks combine customer diligence, monitoring, reporting, controls, and supervision. |
| **BSA (Bank Secrecy Act)** | Core US AML statute and related regulatory framework imposing recordkeeping, reporting, and compliance obligations on covered financial institutions. |
| **CASP (Crypto-Asset Service Provider)** | MiCA term for a regulated provider of specified cryptoasset services in the EU. It overlaps conceptually with FATF's VASP but is a different legal definition. |
| **CDD (Customer Due Diligence)** | Identifying and verifying a customer, understanding the relationship and beneficial owner, assessing risk, and conducting appropriate ongoing monitoring. |
| **CFT (Countering the Financing of Terrorism)** | Measures to prevent, detect, and report financing connected to terrorism. Funds can originate from lawful or unlawful sources, so CFT is not identical to money-laundering detection. |
| **CPF (Counter-Proliferation Financing)** | Measures addressing financing of weapons-of-mass-destruction proliferation, including targeted financial sanctions and related controls. |
| **EDD (Enhanced Due Diligence)** | Additional diligence and monitoring applied to higher-risk customers, relationships, jurisdictions, products, or transactions. It is risk-based, not merely “more documents.” |
| **FATF (Financial Action Task Force)** | Intergovernmental standard setter for AML, CFT, and proliferation-financing controls. FATF Recommendations influence national law but are not directly self-executing statutes. |
| **FIU (Financial Intelligence Unit)** | National authority receiving and analyzing suspicious transaction or activity reports and disseminating intelligence to competent authorities. Examples include FinCEN in the US and MROS in Switzerland. |
| **FinCEN (Financial Crimes Enforcement Network)** | Bureau of the US Treasury that administers and enforces major parts of the BSA framework and serves as the US FIU. |
| **IVMS101** | InterVASP Messaging Standard data model for originator and beneficiary information exchanged to support Travel Rule implementation. It is a messaging standard, not the legal rule itself. |
| **KYB (Know Your Business)** | Customer-diligence processes for legal entities, including formation, activities, ownership, control persons, authority, and expected behavior. |
| **KYT (Know Your Transaction)** | Industry term for transaction monitoring and risk analysis, especially blockchain screening. It is not one universal legal standard or methodology. |
| **QA (Quality Assurance)** | Structured checking of alert logic, investigations, data labels, analyst decisions, and operational outputs for accuracy and consistency. In compliance analytics, QA findings feed model tuning, training, control testing, and audit evidence. |
| **ML (Money Laundering)** | Concealing, converting, transferring, or using criminal proceeds so their illicit origin or control is obscured. Legal elements vary by jurisdiction. |
| **Mixer / tumbler** | Service or protocol designed to combine or transform asset flows to reduce transaction traceability. Use is not automatically proof of crime, but it creates material AML and sanctions risk. |
| **OFAC (Office of Foreign Assets Control)** | US Treasury office administering and enforcing US economic and trade sanctions. Its programs can apply to persons, entities, vessels, and property interests, including digital-asset addresses used as identifiers. |
| **OSINT (Open-Source Intelligence)** | Information collected from publicly accessible sources and analyzed for intelligence. Blockchain attribution combines onchain data with OSINT, proprietary data, and investigative process. |
| **PEP (Politically Exposed Person)** | Individual entrusted with a prominent public function, plus relevant family members and close associates under applicable rules. PEP status calls for risk-sensitive enhanced controls; it does not imply criminal conduct. |
| **Proliferation financing (PF)** | Funding or financial services supporting the development, acquisition, transport, or use of weapons of mass destruction and related materials or actors. |
| **SAR / STR (Suspicious Activity Report / Suspicious Transaction Report)** | Confidential report submitted to an FIU or authority when suspicion criteria are met. The terminology and filing threshold differ by jurisdiction; a filing is not a finding of guilt. |
| **Sanctions screening** | Comparing customers, counterparties, addresses, transactions, vessels, countries, and other attributes against applicable restrictions and risk data. Name matching alone is insufficient for complete sanctions compliance. |
| **Source of funds (SoF)** | Origin of the particular money or assets used in a transaction or relationship, such as salary, sale proceeds, inheritance, or borrowing. |
| **Source of wealth (SoW)** | Explanation of how a person accumulated overall wealth, such as business ownership or long-term employment. It is broader than source of funds. |
| **TBML (Trade-Based Money Laundering)** | Moving or disguising illicit value through trade transactions, for example by mispricing, duplicate invoicing, phantom shipments, or quantity manipulation. |
| **TF (Terrorist Financing)** | Collection or provision of funds or financial services for terrorist purposes or organizations, whether the funds themselves are lawful or criminal in origin. |
| **TRISA / TRUST** | Industry Travel Rule information-sharing networks or protocols. TRISA is the Travel Rule Information Sharing Architecture; TRUST is the Travel Rule Universal Solution Technology network initiated by industry participants. |
| **UBO (Ultimate Beneficial Owner)** | Natural person who ultimately owns or controls a legal entity or arrangement under applicable thresholds and control tests. Nominees and intermediate companies do not end the analysis. |
| **VA (Virtual Asset)** | FATF term for a digital representation of value that can be digitally traded or transferred and used for payment or investment, excluding specified representations already covered elsewhere such as fiat currency or financial assets under FATF definitions. |
| **VASP (Virtual Asset Service Provider)** | FATF term for a person conducting specified virtual-asset activities as a business for or on behalf of another person. National implementation, scope, and licensing terminology vary. |

### Regulators, standard setters, and legal frameworks

| Term or abbreviation | Explanation |
|---|---|
| **BCBS (Basel Committee on Banking Supervision)** | Global standard setter for prudential bank regulation, hosted by the BIS. Basel standards require national implementation and are not directly binding everywhere by themselves. |
| **BIS (Bank for International Settlements)** | International organization serving central banks and hosting committees including BCBS and CPMI. BIS research and standards work are influential but have different legal status from national regulation. |
| **DORA (Digital Operational Resilience Act)** | EU Regulation 2022/2554 establishing ICT risk-management, incident-reporting, resilience-testing, and third-party-risk requirements for covered financial entities. |
| **EBA (European Banking Authority)** | EU authority contributing to banking regulation and supervision and holding specified MiCA responsibilities, including significant ARTs and EMTs. |
| **ECB (European Central Bank)** | Central bank for the euro area and EU institution responsible for euro monetary policy, specified banking-supervision functions, and payment-system roles. |
| **ESMA (European Securities and Markets Authority)** | EU securities-markets authority and standard setter with responsibilities under MiCA and other EU financial-services legislation. |
| **FCA (Financial Conduct Authority)** | United Kingdom conduct regulator for financial services and markets, with prudential responsibilities for some firms and AML registration/supervision roles for relevant cryptoasset businesses. |
| **FDIC (Federal Deposit Insurance Corporation)** | US agency insuring eligible bank deposits within statutory limits, supervising specified banks, and resolving failed insured depository institutions. FDIC insurance does not automatically protect stablecoins or crypto exchange balances. |
| **FINMA (Swiss Financial Market Supervisory Authority)** | Switzerland's federal financial-market supervisor for banks, securities firms, insurers, collective investments, financial-market infrastructures, and AML-supervised activities within its remit. |
| **FSB (Financial Stability Board)** | International body coordinating national authorities and standard setters on global financial stability and policy. Its recommendations require implementation through jurisdictions or other bodies. |
| **IOSCO (International Organization of Securities Commissions)** | Global association and standard setter for securities regulators, covering investor protection, fair and efficient markets, and systemic-risk concerns. |
| **MAS (Monetary Authority of Singapore)** | Singapore's central bank and integrated financial regulator, including payment-services and digital-token activities within its statutory remit. |
| **MiCA (Markets in Crypto-Assets Regulation)** | EU Regulation 2023/1114 establishing rules for cryptoasset issuers, ARTs, EMTs, CASPs, market conduct, disclosure, governance, and supervision. It does not replace other EU law when an instrument is already regulated as a financial instrument. |
| **NIST (National Institute of Standards and Technology)** | US standards and research agency publishing widely used cybersecurity and cryptographic standards and guidance. |
| **NYDFS (New York State Department of Financial Services)** | New York regulator overseeing state-chartered financial entities and virtual-currency businesses licensed under New York's BitLicense or limited-purpose trust frameworks. |
| **OCC (Office of the Comptroller of the Currency)** | US Treasury bureau chartering, regulating, and supervising national banks and federal savings associations. |
| **OECD (Organisation for Economic Co-operation and Development)** | Intergovernmental organization developing economic, tax, governance, and policy standards, including the Crypto-Asset Reporting Framework. |
| **PRA (Prudential Regulation Authority)** | Bank of England authority responsible for prudential regulation and supervision of UK banks, insurers, and specified investment firms. |
| **SFC (Securities and Futures Commission)** | Hong Kong regulator for securities and futures markets and relevant virtual-asset trading-platform activities. |
| **SNB (Swiss National Bank)** | Switzerland's central bank, responsible for monetary policy, banknote issuance, financial-stability contributions, and facilitating payment-system functioning. |
| **VARA (Virtual Assets Regulatory Authority)** | Dubai authority regulating virtual-asset activities in the Emirate of Dubai outside the Dubai International Financial Centre, within its legal mandate. |

### Prudential risk, accounting, and control abbreviations

| Term or abbreviation | Explanation |
|---|---|
| **ALM (Asset-Liability Management)** | Management of balance-sheet interest-rate, liquidity, funding, currency, and maturity risks arising from assets and liabilities together. |
| **AT1 (Additional Tier 1 capital)** | Basel bank-capital category of going-concern loss-absorbing instruments below CET1 in quality and priority, subject to detailed eligibility and write-down or conversion terms. |
| **Basel III** | International bank-prudential framework covering capital, leverage, liquidity, risk measurement, disclosure, and supervision. National implementation and transition dates vary. |
| **CAR (Capital Adequacy Ratio)** | Capital divided by a defined risk exposure measure, commonly risk-weighted assets. The numerator and required threshold depend on regulatory framework and capital tier. |
| **CET1 (Common Equity Tier 1)** | Highest-quality Basel regulatory capital, primarily common shares and retained earnings after regulatory adjustments. |
| **EAD (Exposure at Default)** | Estimated exposure amount when a counterparty defaults, including current drawn amounts and modeled conversion of commitments or future exposure. |
| **ECL (Expected Credit Loss)** | Forward-looking accounting estimate of probability-weighted credit losses, notably under IFRS 9. It differs from regulatory expected loss and economic-capital measures. |
| **ES (Expected Shortfall)** | Average loss beyond a selected quantile threshold under a defined model and horizon. Unlike VaR, it measures the severity of tail outcomes beyond the cutoff. |
| **FVOCI (Fair Value Through Other Comprehensive Income)** | IFRS measurement category in which specified fair-value changes are recognized in OCI, with detailed treatment depending on instrument classification. |
| **FVTPL (Fair Value Through Profit or Loss)** | IFRS measurement category in which fair-value changes are recognized in profit or loss. |
| **GAAP (Generally Accepted Accounting Principles)** | Accounting framework accepted in a jurisdiction. “US GAAP” refers to US standards, while IFRS is a separate global framework used in many jurisdictions. |
| **ICAAP (Internal Capital Adequacy Assessment Process)** | Bank process for assessing capital adequacy relative to its material risks, strategy, and stress scenarios under supervisory frameworks. |
| **IFRS (International Financial Reporting Standards)** | Accounting standards issued by the International Accounting Standards Board under the IFRS Foundation. Application depends on jurisdiction and reporting entity. |
| **ILAAP (Internal Liquidity Adequacy Assessment Process)** | Bank process for assessing liquidity and funding adequacy under normal and stressed conditions. |
| **IRB (Internal Ratings-Based approach)** | Basel credit-risk approach allowing approved banks to use specified internal estimates in regulatory capital calculations, subject to floors and supervisory requirements. |
| **KRI (Key Risk Indicator)** | Metric intended to signal changing risk exposure or control weakness. A threshold breach prompts investigation; it is not itself proof of loss. |
| **LCR (Liquidity Coverage Ratio)** | Basel ratio requiring sufficient high-quality liquid assets to cover modeled net cash outflows over a 30-day stress period. |
| **LGD (Loss Given Default)** | Proportion of exposure expected to be lost after recoveries when default occurs. It reflects collateral, seniority, workout cost, timing, and economic conditions. |
| **NSFR (Net Stable Funding Ratio)** | Basel structural funding ratio comparing available stable funding with required stable funding over a one-year horizon. |
| **OCI (Other Comprehensive Income)** | Accounting presentation category for specified income and expense items recognized outside current-period profit or loss, subject to applicable standards. |
| **PD (Probability of Default)** | Estimated likelihood that an obligor defaults over a defined horizon under a stated default definition. |
| **RCSA (Risk and Control Self-Assessment)** | Structured process in which a business identifies operational risks, assesses inherent and residual risk, and evaluates controls. Independent challenge is needed because “self” assessment can be optimistic. |
| **RPO (Recovery Point Objective)** | Maximum tolerable data loss measured in time: the point to which data must be recoverable after disruption. |
| **RTO (Recovery Time Objective)** | Target time for restoring a service or process after disruption. It differs from the maximum tolerable disruption used in operational-resilience frameworks. |
| **RWA (Risk-Weighted Assets)** | Bank exposures weighted or modeled for credit, market, and operational risk to form a prudential capital denominator. This is unrelated to tokenization's “real-world assets.” |
| **SIEM (Security Information and Event Management)** | Technology aggregating and analyzing security logs and alerts to support monitoring, detection, and incident investigation. |
| **SOC (Security Operations Center)** | Team and operating function monitoring, detecting, analyzing, and responding to cybersecurity events. “SOC report” can separately mean a service-organization controls assurance report. |
| **SPPI (Solely Payments of Principal and Interest)** | IFRS 9 contractual-cash-flow test used with the business model to classify specified financial assets for measurement. |

### Additional risk, accounting, and resolution terms

| Term | Explanation |
|---|---|
| **Bail-in** | Resolution power or contractual mechanism that absorbs losses by writing down or converting eligible creditor claims into equity, recapitalizing a failing institution without relying solely on public funds. |
| **Business continuity** | Capability and plans to continue or restore operations after disruption. Operational resilience begins with important services and tolerated impact rather than only restoring individual systems. |
| **Derecognition** | Removal of an asset or liability from an entity's balance sheet when the applicable accounting criteria are met. Transfer on a ledger does not automatically cause accounting derecognition. |
| **Double-entry accounting** | System in which each transaction affects at least two accounts and total debits equal total credits, preserving the accounting equation. It is different from blockchain's replicated ledger structure. |
| **Fair value** | Under IFRS 13, exit price that would be received to sell an asset or paid to transfer a liability in an orderly transaction between market participants at the measurement date. |
| **Fair-value hierarchy** | Classification of valuation inputs: Level 1 unadjusted active-market prices for identical items; Level 2 other observable inputs; Level 3 significant unobservable inputs. It ranks inputs, not valuation techniques. |
| **Inherent risk** | Risk level before considering controls or mitigation. |
| **Materiality** | Whether omission, misstatement, or obscuring of information could reasonably influence decisions under the applicable reporting or assurance framework. It is context-specific, not one universal percentage. |
| **Model risk** | Risk of adverse decisions or outcomes from incorrect models, flawed assumptions, bad data, implementation error, or use outside the model's valid scope. |
| **Operational resilience** | Ability to deliver important services through disruption within defined tolerances, including dependencies on people, facilities, technology, data, and third parties. |
| **Recognition** | Accounting decision to record an item in financial statements because it meets applicable definition and recognition criteria. Legal ownership, economic exposure, and accounting recognition can diverge. |
| **Recovery** | Actions taken by a distressed but still operating institution to restore financial and operational viability. It is distinct from resolution by public authorities after failure or likely failure. |
| **Residual risk** | Risk remaining after controls and mitigation. A low residual rating depends on controls operating effectively, not merely existing on paper. |
| **Resolution** | Use of statutory powers to manage a failing financial institution while maintaining critical functions, protecting appropriate claimants, and allocating losses under the legal framework. |
| **Risk appetite** | Aggregate amount and types of risk an organization is willing to accept within its capacity to pursue objectives. |
| **Risk capacity** | Maximum risk an organization can absorb before breaching capital, liquidity, legal, operational, or viability constraints. |
| **Risk limit** | Quantified boundary translating appetite and tolerance into exposure controls for portfolios, counterparties, products, or operations. |
| **Risk tolerance** | Permitted variation or exposure around a particular objective or risk type, narrower and more operational than overall appetite. |
| **Stress test** | Forward-looking analysis applying severe but plausible or reverse-engineered scenarios to exposures, earnings, liquidity, capital, operations, or business viability. |
| **Three-lines model** | Governance model separating first-line ownership and control, second-line risk/compliance oversight, and third-line independent internal audit assurance. Exact organization can vary. |

## Interoperability, Privacy, and Enterprise DLT

| Term or abbreviation | Explanation |
|---|---|
| **Atomic swap** | Exchange across assets or networks designed so both transfers complete or neither does, commonly using hash and time locks. Practical atomicity is constrained by chain liveness and finality. |
| **AVS (Actively Validated Service)** | In EigenLayer terminology, a service obtaining cryptoeconomic validation from restaked assets and operators under additional conditions. Each AVS defines its own tasks and slashing risk. |
| **CCTP (Cross-Chain Transfer Protocol)** | Circle protocol for native USDC transfer across supported chains by burning on the source and minting after an attested message on the destination. It is distinct from locking USDC and issuing a third-party wrapper. |
| **CCIP (Cross-Chain Interoperability Protocol)** | Chainlink protocol for cross-chain messaging and token transfer using Chainlink oracle networks, risk-management components, and chain-specific contracts. |
| **Confidential computing** | Processing data inside hardware- or software-isolated environments intended to protect data in use. It complements, rather than replaces, encryption at rest and in transit. |
| **DAML (Digital Asset Modeling Language)** | Smart-contract language and application model developed by Digital Asset for multi-party workflows and used in Canton-related systems. |
| **DApp / dapp (Decentralized application)** | Application whose core state transitions use a blockchain or decentralized protocol. Front ends, APIs, governance, and infrastructure can remain centralized. |
| **DVN (Decentralized Verifier Network)** | LayerZero term for an independently configured verifier network that attests to cross-chain messages under an application's security stack. Multiple DVNs do not help if configuration or dependencies are correlated. |
| **EEA (Enterprise Ethereum Alliance)** | Member organization developing specifications and guidance for enterprise use of Ethereum technology. |
| **FHE (Fully Homomorphic Encryption)** | Encryption allowing computation over ciphertexts so the decrypted result corresponds to computation on plaintext. It provides confidentiality but has substantial performance and key-management trade-offs. |
| **fhEVM** | Zama's FHE-enabled EVM-oriented environment and tooling for confidential smart-contract state and computation. It is not the ordinary public Ethereum EVM. |
| **GMP (General Message Passing)** | Cross-chain architecture conveying arbitrary application messages rather than only fixed asset transfers. Generality increases the importance of authentication and destination-call controls. |
| **HTLC (Hash Time-Locked Contract)** | Conditional transfer requiring revelation of a hash preimage before a deadline, otherwise allowing timeout recovery. Used in payment channels and atomic swaps. |
| **IBC (Inter-Blockchain Communication)** | Protocol family originating in the Cosmos ecosystem for authenticated, ordered or unordered communication between independent ledgers using light-client verification, connections, channels, and relayers. |
| **IBFT (Istanbul Byzantine Fault Tolerance)** | BFT consensus family for permissioned Ethereum networks using a known validator set. Implementations and version behavior differ. |
| **Interoperability** | Ability of different systems to exchange messages, assets, identity, or state with usable semantics. Connectivity alone is not interoperability if recipients cannot verify or interpret the message. |
| **MPC (Multi-Party Computation)** | Cryptographic techniques allowing parties to compute a result jointly without revealing their private inputs to one another. Custody uses MPC/TSS to distribute signing authority; privacy systems use broader MPC computations. |
| **Notary** | Trusted or collectively operated service attesting that an event or state occurred. Corda notaries prevent double-spending and can provide validation, while bridge notaries may authorize cross-chain messages. |
| **OFT (Omnichain Fungible Token)** | LayerZero token standard enabling coordinated token movement across supported chains using burn/mint or lock/unlock adapters and an application-selected verification configuration. |
| **Permissioned ledger** | DLT in which participation, validation, data access, or transaction submission is restricted by identity and governance rules. “Permissioned” does not specify whether validators are independent. |
| **Privacy pool** | Smart-contract system allowing deposits and withdrawals with cryptographic unlinkability, sometimes adding association-set or compliance proofs. Privacy guarantees depend on anonymity set, metadata, relayers, and implementation. |
| **Private transaction manager** | Enterprise Ethereum component that distributes private payloads to authorized parties while anchoring coordination or hashes through a blockchain. Tessera is a historical example. |
| **QBFT (Quorum Byzantine Fault Tolerance)** | Enterprise Ethereum BFT consensus implemented in Hyperledger Besu, using a permissioned validator set and immediate block finality under its quorum assumptions. |
| **Relayer** | Offchain actor carrying transactions, proofs, or messages between components or chains. A permissionless relayer can improve liveness, but verification rules—not the relayer's label—determine whether it can forge messages. |
| **Selective disclosure** | Revealing only required attributes or claims rather than an entire credential or dataset. Zero-knowledge proofs and verifiable credentials can support it. |
| **TEE (Trusted Execution Environment)** | Hardware-isolated execution region intended to protect code and data from the host system. TEEs add manufacturer, firmware, attestation, side-channel, and physical-security assumptions. |
| **TFHE (Torus Fully Homomorphic Encryption)** | FHE family operating over torus-based learning-with-errors constructions, used by Zama libraries for programmable encrypted computation. |
| **TLS (Transport Layer Security)** | Protocol securing data in transit between endpoints with encryption and authentication. TLS protects the connection, not necessarily the endpoint or truth of application data. |
| **ULN (Ultra Light Node)** | LayerZero term for its endpoint and messaging architecture, in which applications configure external verification and execution components instead of running a full source-chain light client on every destination. |
| **VAA (Verifiable Action Approval)** | Wormhole term for a guardian-signed message attesting to an observed cross-chain event. Destination contracts verify the VAA under Wormhole's guardian assumptions. |
| **XCM (Cross-Consensus Messaging)** | Polkadot message format and execution language for instructions across consensus systems, parachains, and related locations. It is not itself the transport channel or bridge security mechanism. |

### Enterprise platforms and organizations

| Name or abbreviation | Explanation |
|---|---|
| **Canton Network** | Privacy-enabled network-of-networks architecture from Digital Asset and ecosystem participants for synchronized transactions across independently governed applications using Canton protocol technology. |
| **Corda** | Permissioned DLT platform initiated by R3 for multi-party business workflows, point-to-point data sharing, contract verification, and notary-based uniqueness consensus. |
| **Enterprise Ethereum** | Use of Ethereum-compatible clients, EVM contracts, and related specifications in permissioned or institutionally governed settings. It is an architectural family, not one network. |
| **Hyperledger** | Linux Foundation umbrella for open-source enterprise blockchain and distributed-ledger projects. It is not a blockchain product itself. |
| **Hyperledger Besu** | Java-based Ethereum client supporting public Ethereum and private networks, including permissioning and enterprise BFT modes such as QBFT. |
| **Hyperledger Cacti** | Interoperability framework for connecting heterogeneous ledgers and business systems through pluggable connectors and transaction-coordination patterns. |
| **Hyperledger Fabric** | Permissioned DLT platform with membership services, channels, chaincode, endorsement policies, and ordering services. It does not use the EVM by default. |
| **Hyperledger FireFly** | Multiparty system and API layer for enterprise blockchain applications, coordinating identities, tokens, data exchange, and blockchain transactions across supported connectors. |
| **Paladin** | Open-source privacy-focused transaction manager and smart-contract platform from Kaleido for combining public EVM settlement with private domains and enterprise workflows. |
| **R3** | Enterprise software company that initiated Corda. The company and the open-source/platform ecosystem should not be treated as identical legal or governance objects. |
| **Zama** | Cryptography company developing open-source FHE libraries, fhEVM technology, and associated confidential-blockchain infrastructure. |

## Companies, Protocols, and Product Names

Company, foundation, DAO, protocol, network, and token are different objects.
The following entries identify recurring names without implying ownership,
endorsement, or a fixed legal classification.

| Name or abbreviation | Explanation |
|---|---|
| **Aave** | DeFi liquidity and lending protocol ecosystem using pooled markets, overcollateralized borrowing, oracle-based health calculations, and permissionless liquidations. Aave Labs, Aave DAO, deployed protocol versions, and AAVE token holders have different roles. |
| **Chainalysis** | Blockchain-data and analytics company providing transaction monitoring, investigations, attribution, and compliance products to public- and private-sector customers. |
| **Chainlink** | Oracle and interoperability ecosystem providing Data Feeds, Data Streams, Automation, VRF, Proof of Reserve, Functions, and CCIP through distinct architectures. “DON” means Decentralized Oracle Network in Chainlink terminology. |
| **Circle** | Financial-technology company and issuer of USDC and EURC under applicable entities and terms; developer of CCTP. Circle is not a central bank. |
| **Coinbase** | Publicly listed crypto company operating exchange, brokerage, custody, prime, wallet, stablecoin-distribution, and infrastructure businesses. Coinbase, Coinbase Custody, Coinbase Exchange, and Base have distinct roles. |
| **Compound** | DeFi lending protocol ecosystem. Compound III, also called Comet, uses a base borrowing asset with supported collateral rather than the earlier pooled cross-asset architecture. |
| **Curve** | DEX and governance ecosystem known for StableSwap pools, vote-escrowed CRV, gauges, and liquidity for stable or correlated assets. |
| **Dune** | Blockchain-data platform offering decoded datasets, SQL queries, dashboards, and community analytics. Its results are derived offchain rather than consensus state. |
| **Elliptic** | Blockchain-analytics company providing wallet and transaction screening, investigations, attribution, and risk-intelligence products. |
| **Euler** | Modular DeFi lending ecosystem with isolated and vault-based market architectures. Version and deployment must be specified because designs changed after incidents and relaunches. |
| **EigenLayer** | Ethereum restaking protocol ecosystem allowing staked assets and operators to provide cryptoeconomic validation to AVSs under additional risks and slashing conditions. |
| **Fireblocks** | Digital-asset custody and transfer infrastructure company using MPC-based wallet technology, policy workflows, APIs, and a network connecting counterparties. It is not itself a blockchain. |
| **Fnality** | Company and network initiative developing regulated payment systems using tokenized central-bank-money-backed settlement assets for wholesale financial markets, subject to jurisdiction-specific arrangements. |
| **GMX** | Onchain spot and perpetual trading protocol ecosystem using pooled liquidity and oracle-influenced execution designs. Token and product versions differ by deployment. |
| **LayerZero** | Cross-chain messaging protocol ecosystem built around endpoint contracts, application-configured DVNs and executors, and standards including OFT. LayerZero Labs is the development company. |
| **Lido** | Liquid-staking protocol and governance ecosystem issuing staking receipt tokens such as stETH through its Ethereum deployment and validator-operator framework. |
| **Liquity** | DeFi borrowing protocol ecosystem. Liquity V1 centers on LUSD; V2 introduces BOLD and materially different market and interest mechanisms. |
| **MakerDAO / Sky** | MakerDAO was the governance and protocol ecosystem behind DAI; it rebranded and reorganized under Sky, with tokens and products including USDS, SKY, DAI, MKR, and Spark-related components. Historical and current names should be dated. |
| **Maple Finance** | Onchain credit and asset-management protocol ecosystem using managed pools and underwriting structures, including institutional and real-world credit exposures. |
| **Merkle Science** | Blockchain-analytics and risk-intelligence company offering transaction monitoring, investigations, attribution, and compliance tooling. It is unrelated to the generic Merkle tree data structure. |
| **Morpho** | DeFi lending protocol ecosystem. Morpho Blue defines immutable isolated markets; MetaMorpho/ERC-4626 vaults and curators package supplier exposure across selected markets. |
| **OpenZeppelin** | Company and open-source ecosystem providing smart-contract libraries, upgrade tooling, governance components, monitoring, and security services. |
| **Paxos** | Regulated financial-technology company and trust-company group associated with stablecoin issuance and tokenized assets including PYUSD, USDP, and PAXG under product-specific terms. |
| **Sky** | Current brand and governance ecosystem succeeding MakerDAO, including USDS, SKY, savings and collateral systems, and affiliated or integrated protocol components. |
| **Spark** | DeFi lending and liquidity ecosystem originating within Maker/Sky, with lending markets and capital-allocation products governed through related structures. |
| **Tether** | Group associated with issuance and operation of USD₮/USDT and other tokens under product terms. The company, token contracts, reserve portfolio, and distribution counterparties are distinct analytical layers. |
| **The Graph** | Blockchain indexing protocol and software ecosystem using subgraphs, Graph Node, indexers, delegators, and GraphQL query interfaces. Indexed data is derived, not native consensus state. |
| **TRM Labs** | Blockchain-intelligence company providing transaction monitoring, sanctions screening, investigations, attribution, and risk analytics. “TRM” is the company name, not a generally standardized technical abbreviation in this context. |
| **Uniswap** | DEX protocol ecosystem spanning several AMM generations. Uniswap Labs, Uniswap Foundation, governance, interfaces, routers, deployed contracts, and the UNI token are distinct components. |

### Additional recurring organizations, products, and protocol terms

| Name or abbreviation | Explanation |
|---|---|
| **BIP-340 / BIP340** | Bitcoin standard specifying Schnorr signatures over secp256k1, used by Taproot. |
| **BNY** | Corporate brand of The Bank of New York Mellon Corporation, a global financial-services company active in custody, asset servicing, clearing, collateral, investment management, and related market infrastructure. “BNY” can refer generically to the parent or group entities, so legal and regulatory analysis must identify the subsidiary actually providing a service. |
| **BRC-20** | Experimental fungible-token convention using ordinal inscriptions and offchain indexing on Bitcoin. It is not a Bitcoin consensus-native token ledger comparable to ERC-20 contract state. |
| **BUIDL** | BlackRock USD Institutional Digital Liquidity Fund tokenized through Securitize structures. A BUIDL token represents a restricted fund interest under offering terms, not a generally redeemable retail stablecoin. |
| **BUSD** | Binance-branded USD stablecoin historically issued by Paxos; new Paxos issuance ceased in 2023 under regulatory direction. Existing tokens and other similarly named contracts must be evaluated by issuer, chain, and redemption status. |
| **CCTC (Coinbase Custody Trust Company)** | New York-chartered limited-purpose trust company providing specified Coinbase institutional custody services. It is a distinct legal entity from Coinbase, Inc. and other group companies. |
| **CREATE2** | EVM opcode that deploys a contract to an address derived from deployer, salt, and initialization-code hash, enabling deterministic addresses. Address predictability does not guarantee future code behavior. |
| **DELEGATECALL** | EVM instruction executing another account's code in the caller's storage, address, and value context. It enables proxies and libraries but can corrupt storage or transfer control if misused. |
| **DTCC (Depository Trust & Clearing Corporation)** | US post-trade market-infrastructure group whose subsidiaries provide depository, clearing, settlement, data, and related services. Product and subsidiary roles should be identified precisely. |
| **EIP-7251** | Ethereum upgrade change increasing the maximum effective balance per validator from the historical 32 ETH cap to support validator consolidation, without eliminating minimum activation requirements or operator risk. |
| **EVC (Ethereum Vault Connector)** | Euler component coordinating user accounts, collateral relationships, batching, and checks across compatible vaults. |
| **EVK (Euler Vault Kit)** | Euler framework for deploying ERC-4626-compatible lending vaults with configurable risk and integration parameters. |
| **FBA (Federated Byzantine Agreement)** | Consensus model in which nodes choose quorum slices of parties they trust rather than using one globally fixed validator set. Safety requires appropriate quorum intersection. Stellar is the canonical example. |
| **FTX** | Crypto exchange group that failed in 2022 after customer-asset, governance, risk, accounting, and affiliated-trading-firm failures. It is used in the course as a case study, not as an active venue recommendation. |
| **GSM (GHO Stability Module)** | Aave mechanism exchanging GHO against approved stablecoins under configured fees and limits. It supports peg liquidity while importing the approved asset's issuer and depeg risk. |
| **HASH160** | Bitcoin convention applying RIPEMD-160 to a SHA-256 hash, used in legacy public-key and script-hash address constructions. |
| **IAM (Identity and Access Management)** | Policies and systems controlling digital identities, authentication, roles, privileges, provisioning, and access review. Key custody does not replace IAM around operational systems. |
| **IIN (Interoperation Identity Network)** | Hyperledger Cacti/Weaver architecture term for a network that exchanges or resolves decentralized identifiers, verifiable credentials, and membership information across ledgers. |
| **IMF (International Monetary Fund)** | International organization supporting monetary cooperation and financial stability through surveillance, lending, capacity development, research, and standards-related work. |
| **Kinexys** | JPMorgan's blockchain and digital-assets business, succeeding the Onyx brand, with products for institutional payments, tokenization, and related infrastructure. Product, bank-entity, and network roles should be distinguished. |
| **LUNA / UST** | Tokens of the original Terra ecosystem. UST was an algorithmic dollar-targeting stablecoin linked economically to LUNA; their 2022 collapse is a central reflexivity and run-risk case study. Later chains and tickers must not be conflated with the failed original structure. |
| **P2PKH (Pay to Public Key Hash)** | Legacy Bitcoin output script locking value to the hash of a public key and requiring a matching public key and signature to spend. |
| **P2SH (Pay to Script Hash)** | Bitcoin output type committing to a redeem script whose conditions are revealed when spent, historically enabling more flexible scripts and multisig addresses. |
| **PBFT (Practical Byzantine Fault Tolerance)** | Classical BFT state-machine-replication protocol using leader proposals and multiple voting phases, commonly tolerating fewer than one-third Byzantine replicas under its assumptions. |
| **PSP (Payment Service Provider)** | Entity providing payment initiation, acquiring, money transmission, e-money, account, or related services under applicable law and business model. It is a broad functional term, not one universal license. |
| **RBF (Replace by Fee)** | Bitcoin transaction-replacement policy allowing an unconfirmed transaction to be replaced by a conflicting version paying a higher fee under node policy. |
| **SDX (SIX Digital Exchange)** | SIX group infrastructure for regulated digital securities issuance, trading, settlement, and custody services in Switzerland and connected markets. |
| **SIX** | Swiss financial-market-infrastructure group operating exchange, post-trade, financial-information, and payment-related businesses. The brand is a name, not normally expanded as a current acronym. |
| **SPK** | Governance and ecosystem token associated with Spark. Token rights, distribution, and its relationship to Sky governance are product- and time-specific. |
| **XRPL (XRP Ledger)** | Public distributed ledger using a trust-list-based consensus process and native XRP asset. It does not use PoW mining. |

## Custody Types

| Type | Simple meaning | Example | Pros | Risks / trade-offs |
|---|---|---|---|---|
| **Self-custody** | You control the private keys yourself. | Hardware wallet or self-managed software wallet. | Maximum direct control; no exchange or custodian can freeze or misuse assets by itself. | Lose the key or seed phrase and you may lose assets permanently; phishing and operational mistakes are your responsibility. |
| **Third-party custody** | A company controls keys or asset movement for you. | Crypto exchange account or institutional crypto custodian. | Easier recovery, compliance, reporting, institutional controls. | You take custodian solvency, operational, legal, and counterparty risk. |
| **Qualified / regulated custody** | A regulated custodian holds assets under specific legal and operational rules. | Institutional digital asset custody provider or bank custody service. | Better fit for institutions, audits, segregation, controls, insurance possibilities. | More expensive; may restrict asset access, DeFi use, or transfer speed. |
| **Multi-signature custody** | Asset movement requires multiple keys to approve. | 2-of-3 wallet requiring user, backup, and service provider signatures. | Reduces single-key failure; useful for teams and treasuries. | More operational complexity; bad key governance can still block access. |
| **MPC custody** | Private-key control is split into cryptographic shares, so no one party holds the full key. | Institutional wallet infrastructure using distributed signing. | Strong operational security; flexible approval workflows. | More complex; relies on correct implementation and vendor/process controls. |

### Custody and wallet operations

| Term or abbreviation | Explanation |
|---|---|
| **Air gap** | Physical or logical isolation intended to prevent a signing system from directly connecting to untrusted networks. Data still crosses the boundary through controlled media or devices, which remains a security path. |
| **Allowlist / whitelist** | List of pre-approved destination addresses, contracts, assets, or actions. It reduces accidental or unauthorized transfers but depends on secure enrollment and change approval. |
| **Cold wallet / cold storage** | Key-management environment kept offline or strongly isolated from transaction networks, trading convenience, and ordinary application access. Cold storage reduces online attack exposure while slowing operations. |
| **Derivation path** | Ordered path specifying which child key or address to derive from an HD-wallet seed, such as a BIP-44-style path. Using the wrong path can make a valid backup appear empty. |
| **Hot wallet** | Wallet connected to online systems and available for frequent or automated signing. It supports liquidity and operations but has greater exposure to remote compromise. |
| **Key ceremony** | Controlled, witnessed procedure for generating, backing up, distributing, activating, rotating, or destroying cryptographic keys or shares. Evidence and separation of duties are as important as cryptography. |
| **Key share** | Secret value held by one MPC/TSS participant and used jointly to produce signatures. A share is not necessarily a literal fragment that can be concatenated into a private key. |
| **Omnibus wallet/account** | Structure pooling assets for several customers in one onchain address or custody account while the intermediary's books track beneficial interests. It improves operational efficiency but increases reconciliation and shortfall risk. |
| **Policy engine** | System applying transaction rules before signing or release, such as thresholds, roles, velocity limits, destination allowlists, time locks, and human approvals. |
| **Qualified custodian** | Legal category under applicable investment or financial regulation for entities eligible to hold specified client assets. The meaning is jurisdiction- and rule-specific; a technically secure wallet provider is not automatically a qualified custodian. |
| **Segregated wallet/account** | Structure in which a client's assets are separated from those of the custodian or other clients at the ledger, account, or legal-record level. Technical address segregation does not alone establish insolvency protection. |
| **Signing quorum** | Minimum number or weight of authorized keys, shares, or approvers required to authorize a transaction. It may be cryptographic, operational, or both. |
| **Sweep** | Operational transfer consolidating balances from deposit addresses into treasury or custody wallets, or moving excess assets from hot to colder storage. |
| **WalletConnect** | Open protocol ecosystem for connecting wallets to applications and relaying session requests. It does not custody assets; users still depend on wallet validation and understandable signing. |

## Related Notes

- [Money, Banking, and Balance
  Sheets](../../01-financial-foundations/01-money-banking-and-payments/money-banking-and-balance-sheets.md)
- [Financial Market
  Infrastructure](../../01-financial-foundations/02-financial-markets/financial-market-infrastructure.md)
- [Financial Regulation, Compliance, and
  Accounting](../../01-financial-foundations/03-risk-and-regulatory-foundations/financial-regulation-compliance-and-accounting.md)
- [Blockchain
  Fundamentals](../../02-blockchain-foundations/01-core-architecture/blockchain-fundamentals.md)
- [Smart Contracts, Virtual Machines, and Token
  Standards](../../02-blockchain-foundations/03-execution-and-applications/smart-contracts-virtual-machines-and-token-standards.md)
- [Blockchain Scaling and Modular
  Architecture](../../02-blockchain-foundations/04-scaling-and-modularity/blockchain-scaling-and-modular-architecture.md)
- [Digital Assets, Token Taxonomy, and
  Economics](../../03-digital-assets-and-market-structure/01-assets-and-economics/digital-assets-token-taxonomy-and-economics.md)
- [DeFi Architecture, Composability, and
  Governance](../../04-decentralized-finance/01-defi-foundations/defi-architecture-composability-and-governance.md)
- [Stablecoins](../../05-digital-money-and-tokenization/01-stablecoins/stablecoins.md)
- [Blockchain Interoperability and
  Bridges](../../06-interoperability-privacy-and-enterprise-dlt/01-interoperability/blockchain-interoperability-and-bridges.md)
- [Blockchain
  Analytics](../../07-compliance-analytics-regulation-and-security/01-aml-and-blockchain-analytics/blockchain-analytics.md)
- [Digital-Asset
  Regulation](../../07-compliance-analytics-regulation-and-security/02-regulation/digital-asset-regulation.md)

## References

### Finance, payments, risk, and accounting

- CPMI, [Glossary of payments and market-infrastructure
  terminology](https://www.bis.org/cpmi/publ/d00b.htm).
- CPMI-IOSCO, [Principles for Financial Market
  Infrastructures](https://www.bis.org/cpmi/publ/d101.htm), 2012.
- Basel Committee on Banking Supervision,
  [Basel Framework](https://www.bis.org/basel_framework/).
- Bank for International Settlements,
  [The monetary system of the future: from vision to
  reality](https://www.bis.org/publ/arpdf/ar2025e3.htm), 2025.
- People's Bank of China,
  [Progress on Research and Development of e-CNY in
  China](https://www.pbc.gov.cn/en/3688110/3688172/4157443/4293696/2021072014364791207.pdf).
- IFRS Foundation,
  [IFRS Accounting Standards](https://www.ifrs.org/issued-standards/list-of-standards/).
- U.S. Securities and Exchange Commission, Investor.gov,
  [Investment products](https://www.investor.gov/introduction-investing/investing-basics/investment-products).
- SWIFT, [About us](https://www.swift.com/about-us).
- European Central Bank,
  [What is TARGET2-Securities?](https://www.ecb.europa.eu/paym/target/t2s/html/index.en.html).
- CLS, [CLSSettlement](https://www.cls-group.com/products/settlement/clssettlement/).

### Regulation, AML, and sanctions

- Financial Action Task Force,
  [Updated Guidance for a Risk-Based Approach to Virtual Assets and
  VASPs](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html).
- Financial Action Task Force,
  [FATF glossary](https://www.fatf-gafi.org/en/pages/fatf-glossary.html).
- European Union,
  [Regulation (EU) 2023/1114 on Markets in
  Crypto-Assets](https://eur-lex.europa.eu/eli/reg/2023/1114/oj).
- European Union,
  [Regulation (EU) 2022/2554 on Digital Operational
  Resilience](https://eur-lex.europa.eu/eli/reg/2022/2554/oj).
- U.S. Congress,
  [S. 1582—GENIUS Act](https://www.congress.gov/bill/119th-congress/senate-bill/1582).
- U.S. Department of the Treasury,
  [OFAC Sanctions Compliance Guidance for the Virtual Currency
  Industry](https://ofac.treasury.gov/media/913571/download).
- Financial Crimes Enforcement Network,
  [What we do](https://www.fincen.gov/what-we-do).
- U.S. Securities and Exchange Commission,
  [Framework for “Investment Contract” Analysis of Digital
  Assets](https://www.sec.gov/corpfin/framework-investment-contract-analysis-digital-assets),
  2019.

### Blockchain, cryptography, and standards

- National Institute of Standards and Technology,
  [Blockchain Technology Overview (NISTIR
  8202)](https://csrc.nist.gov/pubs/ir/8202/final), 2018.
- Satoshi Nakamoto,
  [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf),
  2008.
- Bitcoin Developer Guide,
  [Developer documentation](https://developer.bitcoin.org/devguide/).
- Ethereum.org,
  [Ethereum development documentation](https://ethereum.org/developers/docs/).
- Ethereum Improvement Proposals,
  [EIP index](https://eips.ethereum.org/).
- Ethereum Consensus Specifications,
  [Consensus specifications](https://github.com/ethereum/consensus-specs).
- Solidity,
  [Contract ABI specification](https://docs.soliditylang.org/en/latest/abi-spec.html).
- W3C,
  [Decentralized Identifiers](https://www.w3.org/TR/did-core/) and
  [Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model-2.0/).
- IPFS,
  [Concepts](https://docs.ipfs.tech/concepts/).
- NIST,
  [FIPS 197: Advanced Encryption Standard](https://csrc.nist.gov/pubs/fips/197/final).

### Scaling, interoperability, privacy, and enterprise DLT

- Cosmos,
  [IBC protocol documentation](https://ibcprotocol.dev/).
- CometBFT,
  [Documentation](https://docs.cometbft.com/).
- Polkadot,
  [Consensus](https://wiki.polkadot.com/learn/learn-consensus/).
- Chainlink,
  [Documentation](https://docs.chain.link/).
- Circle,
  [Cross-Chain Transfer Protocol](https://developers.circle.com/cctp).
- LayerZero,
  [Protocol architecture](https://docs.layerzero.network/v2/concepts/layerzero-protocol-architecture).
- Wormhole,
  [VAAs](https://wormhole.com/docs/protocol/infrastructure/vaas/).
- Zama,
  [fhEVM documentation](https://docs.zama.ai/fhevm) and
  [TFHE-rs documentation](https://docs.zama.ai/tfhe-rs).
- LF Decentralized Trust,
  [Paladin](https://www.lfdecentralizedtrust.org/projects/paladin).
- Hyperledger Besu,
  [Documentation](https://docs.besu-eth.org/).
- Hyperledger Fabric,
  [Documentation](https://hyperledger-fabric.readthedocs.io/).
- Hyperledger Cacti,
  [Documentation](https://hyperledger-cacti.github.io/cacti/).
- Hyperledger FireFly,
  [Documentation](https://hyperledger.github.io/firefly/latest/).
- R3,
  [Corda documentation](https://docs.r3.com/).
- Digital Asset,
  [Canton Network](https://www.canton.network/) and
  [Daml documentation](https://docs.digitalasset.com/).

### Protocols, issuers, analytics, and infrastructure companies

- Aave, [Protocol documentation](https://aave.com/docs).
- Morpho, [Protocol documentation](https://docs.morpho.org/).
- Sky, [Protocol documentation](https://developers.skyeco.com/).
- Spark, [Documentation](https://docs.spark.fi/).
- Compound, [Documentation](https://docs.compound.finance/).
- Euler, [Documentation](https://docs.euler.finance/).
- Maple Finance, [Documentation](https://docs.maple.finance/).
- Uniswap, [Protocol documentation](https://docs.uniswap.org/).
- Curve, [Documentation](https://docs.curve.finance/).
- EigenLayer, [Documentation](https://docs.eigenlayer.xyz/).
- Lido, [Ethereum documentation](https://docs.lido.fi/).
- Liquity, [Documentation](https://docs.liquity.org/).
- The Graph, [Documentation](https://thegraph.com/docs/).
- Dune, [Documentation](https://docs.dune.com/).
- Coinbase Global,
  [Investor relations and filings](https://investor.coinbase.com/).
- Coinbase,
  [Licenses and regulated entities](https://www.coinbase.com/legal/licenses).
- BNY,
  [Company overview and legal-entity clarification](https://www.bny.com/corporate/global/en/about-us/).
- DTCC, [Digital Assets](https://www.dtcc.com/digital-assets).
- SIX Digital Exchange, [About SDX](https://www.sdx.com/).
- Securitize,
  [BlackRock launches BUIDL](https://investors.securitize.io/news/news-details/2024/BlackRock-Launches-Its-First-Tokenized-Fund-BUIDL-on-the-Ethereum-Network-03-20-2024/default.aspx).
- Kinexys by J.P. Morgan,
  [About Kinexys](https://www.jpmorgan.com/kinexys/about).
- Circle, [Transparency and reserve management](https://www.circle.com/transparency).
- Tether, [Transparency](https://tether.to/en/transparency/).
- Paxos, [Transparency](https://www.paxos.com/transparency).
- New York State Department of Financial Services,
  [Paxos and BUSD order](https://www.dfs.ny.gov/consumers/alerts/Paxos_and_Binance).
- Fireblocks, [Platform overview](https://www.fireblocks.com/platforms/).
- Fnality, [About Fnality](https://www.fnality.org/about).
- Chainalysis, [Blockchain intelligence](https://www.chainalysis.com/blockchain-intelligence/).
- Elliptic, [Blockchain analytics solutions](https://www.elliptic.co/solutions).
- TRM Labs,
  [Blockchain intelligence platform](https://www.trmlabs.com/blockchain-intelligence-platform).
- Merkle Science,
  [Platform and products](https://www.merklescience.com/).
- U.S. Department of Justice,
  [FTX founder sentenced for fraud](https://www.justice.gov/archives/opa/pr/samuel-bankman-fried-sentenced-25-years-his-orchestration-multiple-fraudulent-schemes).
- U.S. Securities and Exchange Commission,
  [Terraform and Kwon judgment following fraud
  verdict](https://www.sec.gov/newsroom/press-releases/2024-73).
