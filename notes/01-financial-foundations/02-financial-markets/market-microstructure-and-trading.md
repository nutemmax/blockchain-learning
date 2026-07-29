# Market Microstructure And Trading

Market microstructure studies how trading rules, participants, information,
technology, and inventory produce observable prices and liquidity. Two venues
can list economically identical assets yet generate different spreads,
execution quality, and resilience because their matching, disclosure, access,
fee, and market-making arrangements differ.

The "market price" is therefore not a single abstract truth. It is an outcome
formed at a place, time, size, and set of trading conditions.

## What A Market Must Do

A functioning market coordinates:

- buyers and sellers;
- price discovery;
- order submission and matching;
- liquidity provision;
- risk transfer;
- trade confirmation;
- clearing and settlement;
- surveillance and rule enforcement;
- market data distribution; and
- default and disruption management.

Trading is only one stage of the lifecycle. See
[Financial Market Infrastructure](financial-market-infrastructure.md) for
clearing, CCPs, CSDs, custody, and settlement.

## Participants And Roles

### Investor

An investor takes exposure for return, liability matching, hedging, liquidity,
policy, or strategic objectives. Investors range from households to funds,
insurers, pension plans, corporates, sovereigns, and treasuries.

### Broker

A broker acts as agent, seeking execution for a client. It may route orders,
provide algorithms, aggregate venues, arrange block trades, and charge
commission or embedded spread.

### Dealer

A dealer trades as principal, buying or selling for its own account. It provides
immediacy but assumes inventory and adverse-selection risk.

### Market Maker

A market maker repeatedly expresses willingness to buy and sell. It attempts to
earn spread and venue incentives while managing:

- inventory;
- price movements;
- informed counterparties;
- hedging cost;
- funding and capital;
- technology latency;
- operational risk.

Market makers do not guarantee unlimited liquidity. They widen, reduce size, or
withdraw when risk or uncertainty rises.

### Exchange

An exchange operates a market under rules governing listing, access, matching,
data, conduct, and surveillance. It may use an order book, auctions, request for
quote, or hybrid mechanisms.

### Alternative Trading System And Dark Venue

Non-exchange venues can match participants under alternative rules. Dark pools
limit pre-trade transparency to reduce information leakage for large orders,
while creating questions about price formation and access.

### Principal Trading Firm

A principal trading firm uses its own capital, often with automated strategies,
to make markets, arbitrage prices, or trade signals. It is not necessarily a
broker handling customers.

### Prime Broker

A prime broker provides an integrated set of financing, custody, clearing,
securities lending, reporting, and operational services to active clients such
as hedge funds. Prime brokerage creates concentrated counterparty, collateral,
and funding relationships.

## Orders And Quotes

### Bid, Ask, And Midpoint

The best bid is the highest displayed buying price. The best ask is the lowest
displayed selling price.

```text
Quoted spread = P_ask - P_bid
```

```text
Midpoint =
(P_ask + P_bid) / 2
```

The relative quoted spread is often expressed as:

```text
Relative spread =
(P_ask - P_bid) / P_mid
```

The spread compensates liquidity providers for processing, inventory,
adverse-selection, capital, and market risk. It is also affected by tick size,
fees, competition, volatility, and trading activity.

### Market Order

A market order prioritizes execution over price. It consumes available
liquidity and can fill at several price levels. "Market" does not guarantee the
last traded or currently displayed price, especially in a thin or fast market.

### Limit Order

A limit order sets a worst acceptable price. It provides execution price
control but may never fill. A buy limit can execute at or below its limit; a
sell limit at or above.

### Stop Order

A stop order becomes active when a trigger price is reached. Depending on the
implementation it then becomes a market or limit order. Gaps and volatility can
produce execution far from the stop trigger.

### Pegged, Iceberg, And Conditional Orders

- **pegged:** price follows a reference such as the best bid or midpoint;
- **iceberg or reserve:** displays only part of total size;
- **immediate-or-cancel:** executes available size immediately and cancels the
  rest;
- **fill-or-kill:** requires immediate complete execution;
- **post-only:** cancels or reprices if it would immediately take liquidity;
- **all-or-none or minimum quantity:** constrains partial fills.

Order behavior depends on venue rules. Identical labels can hide different
priority and trigger semantics.

## The Central Limit Order Book

A central limit order book ranks bids and asks. A common priority is:

1. best price;
2. earliest time at that price.

Other systems use pro rata allocation, size priority, or special order classes.

### Example

| Ask quantity | Ask price |
|---:|---:|
| 40 | 100.30 |
| 50 | 100.20 |
| 25 | 100.10 |

| Bid price | Bid quantity |
|---:|---:|
| 100.00 | 30 |
| 99.90 | 60 |
| 99.80 | 100 |

The best market is 100.00 bid / 100.10 ask. A market buy for 60 units would
consume 25 at 100.10 and 35 at 100.20 if no other orders arrive.

Volume-weighted average execution price:

```text
VWAP_execution
= (25(100.10)+35(100.20)) / (60)
= 100.1583
```

The difference between expected and realized price is one form of slippage.

```mermaid
flowchart LR
    Orders["Incoming orders"]
    Risk["Validation, limits, and controls"]
    Book["Order book"]
    Match["Matching engine"]
    Trades["Executions"]
    Data["Market data"]
    Post["Clearing and settlement"]
    Orders --> Risk --> Book --> Match --> Trades --> Post
    Book --> Data
    Trades --> Data
```

## Auctions And Continuous Trading

### Continuous Market

Orders match whenever compatible prices exist. This provides immediacy but can
fragment liquidity over time.

### Call Auction

Orders accumulate and the venue selects a clearing price that maximizes
executable volume subject to tie-break rules. Opening, closing, volatility, and
periodic auctions concentrate liquidity and can improve price discovery when
continuous trading is thin.

### Request For Quote

A client requests prices from one or more dealers, commonly for bonds,
derivatives, large orders, or less standardized instruments. RFQ markets expose
less order-book information and rely more on dealer balance sheets.

## Exchange And Over-The-Counter Markets

**Exchange trading** uses a formal venue with standardized rules and often
pre- and post-trade transparency.

**OTC trading** is negotiated bilaterally or through dealer and electronic
networks outside a centralized exchange. OTC does not mean manual: sophisticated
electronic RFQ, streaming quote, and matching systems are common.

OTC markets support customized size, terms, credit, and confidentiality, while
creating counterparty, valuation, transparency, and documentation complexity.

## Liquidity

Liquidity has several dimensions:

- **tightness:** low cost to trade, often proxied by spread;
- **depth:** substantial quantity available near the current price;
- **breadth:** orders distributed across prices and participants;
- **immediacy:** ability to execute quickly;
- **resilience:** speed with which price and depth recover after a shock.

High daily volume does not guarantee liquidity for a large urgent order during
stress. Reported volume can include repeated interdealer trading, wash activity,
or small trades that say little about executable depth.

### Market Impact

A large order moves price because it consumes liquidity and reveals possible
information. Total execution cost includes:

- explicit commission and venue fees;
- bid-ask spread;
- delay cost;
- market impact;
- opportunity cost of unfilled quantity;
- tax and clearing cost.

### Implementation Shortfall

For a buy order, a simplified implementation shortfall is:

```text
IS
= Σ_i (q_i × P_i)
+ q_uP_final
- QP_decision
+ fees
```

where `q_i` and `P_i` are executed quantities and prices, `q_u` is unexecuted
quantity valued at a later price, `Q` is intended quantity, and
`P_decision` is the price when the decision was made.

The framework separates execution performance from whether the investment idea
was good.

## Price Discovery

Price discovery aggregates heterogeneous information and willingness to trade.
The most informative venue need not have the greatest reported volume; it may
lead price changes because its participants, transparency, or instruments react
first.

Prices across venues remain aligned through arbitrage, but arbitrage is limited
by:

- transfer and settlement delay;
- short-sale and borrow constraints;
- funding and margin;
- counterparty risk;
- fees;
- position limits;
- asset or contract differences;
- operational capacity.

Crypto markets demonstrate these limits clearly. The same asset can trade at
different prices across exchanges because balances cannot move instantly, fiat
rails close, withdrawal is suspended, or the venue itself is risky.

## Information And Adverse Selection

A liquidity provider risks trading against someone with better information.
After selling to an informed buyer, the price may rise; after buying from an
informed seller, it may fall. This **adverse selection** is a central reason
spreads widen around news or uncertainty.

Market makers respond by:

- widening quotes;
- reducing size;
- increasing hedging;
- shortening quote life;
- skewing prices to reduce inventory;
- withdrawing from selected instruments.

## Inventory Risk

A dealer that buys from clients accumulates a long position. It can:

- sell to another client;
- hedge with the same or a related instrument;
- trade on another venue;
- warehouse the exposure;
- adjust quotes to encourage offsetting flow.

A dealer's quote is therefore a function of fair-value estimate, inventory,
risk limits, expected client information, hedge liquidity, and balance-sheet
cost—not merely a markup around a public price.

## Fragmentation And Routing

An asset may trade on many exchanges, dealer platforms, dark pools, and internal
systems. A broker or smart order router chooses where and how to execute.

Routing factors include:

- displayed and hidden liquidity;
- price and likelihood of fill;
- venue and rebate economics;
- latency;
- order information leakage;
- clearing and settlement;
- counterparty and venue risk;
- regulatory best-execution obligations.

Fragmentation can increase competition but split liquidity and complicate the
definition of a consolidated best price.

### Internalization

A broker-dealer can execute customer flow against its own inventory or match it
internally. This can save venue cost and provide price improvement, but creates
conflicts between agency duty and principal profit.

### Maker-Taker Fees

Some venues charge orders that remove liquidity and rebate orders that add it.
Quoted spread can therefore differ from the economically realized spread after
fees. Fee incentives may also affect routing and queue competition.

## Execution Quality

No single metric is sufficient.

| Metric | Question |
|---|---|
| Fill rate | How much of the order executed? |
| Speed | How long did execution take? |
| Price improvement | Was execution better than the reference quote? |
| Effective spread | How far was execution from midpoint? |
| Realized spread | How much spread remained after later price movement? |
| Market impact | How did the order move the market? |
| Implementation shortfall | What was total cost versus decision price? |
| Adverse selection | Did price move systematically after fills? |

For trade price `P_t` and midpoint `M_t`, a signed effective spread is commonly
approximated as:

```text
Effective spread=2D(P_t-M_t)
```

where `D=+1` for buyer-initiated and `D=-1` for seller-initiated trades.

Benchmarks can be gamed or inappropriate. VWAP rewards matching the market's
volume distribution; arrival price emphasizes decision-to-execution cost;
closing-price benchmarks can concentrate activity at the close.

## Leverage, Margin, And Liquidation

Leverage magnifies exposure relative to equity:

```text
Leverage =
(gross or net exposure) / (equity)
```

Different definitions produce different ratios. Gross notional, delta-adjusted
exposure, accounting assets, and risk-weighted assets are not interchangeable.

### Margin

Initial margin supports opening a position. Maintenance margin is the minimum
equity level before additional collateral or liquidation is required.

If asset value falls while debt remains fixed, equity falls faster:

| Position | Initial | After 20% asset decline |
|---|---:|---:|
| Asset | 100 | 80 |
| Debt | 60 | 60 |
| Equity | 40 | 20 |

A 20% asset loss caused a 50% equity loss.

Forced liquidation can create feedback:

```mermaid
flowchart TD
    Shock["Price shock"]
    Margin["Margin calls"]
    Sales["Forced sales"]
    Impact["Lower prices and wider spreads"]
    Loss["More losses"]
    Shock --> Margin --> Sales --> Impact --> Loss --> Margin
```

## Prime Brokerage

Prime services can include:

- custody and asset servicing;
- margin lending;
- derivatives and synthetic financing;
- securities borrowing and lending;
- trade clearing and settlement;
- cash management;
- capital introduction;
- consolidated reporting.

The prime broker sees a broad portfolio and can offer cross-margining, but the
relationship creates wrong-way risk and concentration. A client failure can
leave the broker with illiquid positions; a broker failure can trap the
client's assets and hedges.

## Market Abuse And Surveillance

Market integrity threats include:

- insider trading;
- manipulation;
- spoofing and layering;
- wash trading;
- marking the close;
- pump-and-dump schemes;
- front running;
- misuse of customer order information;
- false or misleading disclosures.

Surveillance combines orders, cancellations, trades, accounts, communications,
beneficial ownership, cross-venue data, and event context. A suspicious pattern
is evidence for investigation, not automatically proof of legal violation.

Public blockchains make transaction records visible but do not automatically
identify controllers, reveal offchain arrangements, or distinguish legitimate
arbitrage from collusion.

## Market Stress

During stress:

- correlations can rise;
- market makers protect capital;
- order-book depth falls;
- spreads widen;
- volatility triggers more margin;
- asset sales depress collateral values;
- data and models become less reliable;
- exchanges can apply volatility controls or halt trading.

Historical average volume and spread are poor estimates of stressed
liquidation capacity. Stress tests should include nonlinear price impact,
crowded exits, closed venues, reduced borrow, and delayed settlement.

## Centralized And Decentralized Market Design

| Feature | Central limit order book | Dealer/RFQ market | Automated market maker |
|---|---|---|---|
| Price source | Orders | Dealer quotes | Pool function and arbitrage |
| Liquidity provider | Limit-order traders | Dealer balance sheet | Deposited assets |
| Execution | Matching engine | Bilateral acceptance | Smart-contract swap |
| Inventory risk | Market makers and traders | Dealer | Liquidity providers |
| Transparency | Venue-specific | Often lower pre-trade | Pool state visible |
| Main constraints | Tick, queue, latency, access | Dealer capacity and credit | Curve, pool depth, gas, MEV |

AMMs replace the order book, not the economic need for liquidity, pricing,
arbitrage, and risk bearing. They are developed in
[Decentralized Exchanges And Automated Market Makers](../../03-digital-assets-and-market-structure/03-decentralized-markets/decentralized-exchanges-and-automated-market-makers.md).

## Analytical Checklist

For any trading venue or market:

1. What instruments and contract specifications trade?
2. Who can access directly and through intermediaries?
3. Is trading order-driven, quote-driven, auction, RFQ, AMM, or hybrid?
4. What information is visible before and after trading?
5. How are orders prioritized and matched?
6. Who supplies liquidity and bears inventory risk?
7. What are explicit and implicit trading costs?
8. How fragmented is liquidity, and how are orders routed?
9. What credit, margin, and collateral arrangements apply?
10. How do clearing and settlement work?
11. Which benchmarks measure execution?
12. How are manipulation, conflicts, and outages controlled?
13. What happens when volatility rises and liquidity providers withdraw?

## Connections

- [Securities And Financial Instruments](securities-and-financial-instruments.md)
  explains what is being traded.
- [Financial Market Infrastructure](financial-market-infrastructure.md)
  explains the full trade lifecycle.
- [Financial Risk Management](../03-risk-and-regulatory-foundations/financial-risk-management.md)
  develops market, counterparty, liquidity, and model risk.
- [Crypto Market Structure And Centralized Exchanges](../../03-digital-assets-and-market-structure/02-centralized-markets/crypto-market-structure-and-centralized-exchanges.md)
  applies these concepts to crypto venues.

## References

- U.S. Securities and Exchange Commission,
  [Market centers: buying and selling stock](https://www.sec.gov/answers/market.htm)
- U.S. Securities and Exchange Commission,
  [Guide to broker-dealer registration](https://www.sec.gov/about/divisions-offices/division-trading-markets/division-trading-markets-compliance-guides/guide-broker-dealer-registration)
- Financial Industry Regulatory Authority,
  [Order types](https://www.finra.org/investors/investing/investment-products/stocks/order-types)
- U.S. Securities and Exchange Commission,
  [Research and analysis: market structure](https://www.sec.gov/featured-topics/market-structure-analytics/research-analysis-market-structure)
- International Organization of Securities Commissions,
  [Objectives and principles of securities regulation](https://www.iosco.org/library/pubdocs/pdf/IOSCOPD561.pdf)
- Bank for International Settlements,
  [Market liquidity: research findings and selected policy implications](https://www.bis.org/publ/cgfs11.htm)
- Bank for International Settlements,
  [Repo market functioning](https://www.bis.org/publ/cgfs59.htm)
