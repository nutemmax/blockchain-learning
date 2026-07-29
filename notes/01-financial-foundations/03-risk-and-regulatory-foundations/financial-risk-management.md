# Financial Risk Management

Risk is the possibility that actual outcomes differ materially from intended
outcomes. Financial risk management does not seek to eliminate all uncertainty:
an institution earns returns by accepting selected risks. It seeks to identify,
measure, price, limit, control, monitor, and survive those risks without
violating obligations or transferring unacceptable harm to customers and the
financial system.

Risk categories are analytical lenses, not isolated boxes. A cyber incident can
become an operational outage, cause missed settlement, create liquidity needs,
trigger customer withdrawals, damage reputation, and ultimately threaten
solvency.

## The Risk Management Cycle

Risk management is a feedback process, not an annual inventory. A firm identifies
how it can fail, measures current exposure against appetite, chooses controls,
observes whether those controls operate, and changes the model as products and
conditions evolve. Incidents and near misses feed back into every earlier stage.

```mermaid
flowchart LR
    Identify["Identify exposures and dependencies"]
    Measure["Measure normal and stressed risk"]
    Decide["Accept, avoid, transfer, or mitigate"]
    Control["Limits, collateral, hedges, and controls"]
    Monitor["Monitor indicators and exceptions"]
    Respond["Escalate, recover, and learn"]
    Identify --> Measure --> Decide --> Control --> Monitor --> Respond --> Identify
```

Effective management requires:

- clear ownership;
- complete and timely data;
- independent challenge;
- limits tied to risk capacity;
- escalation with real authority;
- stress and reverse-stress testing;
- contingency and recovery plans;
- incentives consistent with long-term outcomes.

## Risk Capacity, Appetite, Tolerance, And Limits

These terms connect strategy to daily decisions. Capacity is an outer survival
constraint: a firm cannot rationally choose an appetite above the loss or
disruption it can absorb. Appetite translates business strategy into the risk the
board is willing to accept. Tolerance recognizes that actual outcomes fluctuate,
while limits allocate the aggregate appetite to desks, products, entities, and
specific risk factors.

For example, a custodian may have capacity to absorb a large operational loss but
almost no appetite for losing client assets. It can express that low appetite
through transaction limits, independent approvals, address allowlists, and a
maximum hot-wallet balance. A limit breach is not automatically a loss; it is an
early indication that actual exposure has moved outside the approved operating
envelope.

- **risk capacity:** maximum loss or disruption the organization can absorb
  before breaching capital, liquidity, legal, or viability constraints;
- **risk appetite:** types and aggregate levels of risk it deliberately accepts;
- **risk tolerance:** acceptable variation around objectives;
- **limits:** operational quantitative or qualitative boundaries.

Limits can apply by counterparty, issuer, asset, sector, country, currency,
product, maturity, risk factor, wallet, smart contract, venue, or settlement
route. A limit is ineffective if exposures cannot be aggregated promptly or
breaches are routinely waived.

## Credit Risk

Credit risk is loss caused by an obligor failing to perform.

### Expected Loss

A common simplified formulation is:

```text
Expected loss
= PD × LGD × EAD
```

where:

- `PD` is probability of default;
- `LGD` is loss given default;
- `EAD` is exposure at default.

For a portfolio across time, the calculation is more complex: default,
exposure, recovery, correlation, discounting, guarantees, and economic
conditions can all vary.

Expected loss is a pricing and provisioning concept. Capital protects against
unexpected loss beyond the expected amount, subject to the chosen confidence
and regulatory framework.

The three inputs are connected. A deteriorating borrower may draw an unused
credit line before default, increasing EAD. Collateral value may fall for the
same reason the borrower fails, increasing LGD through wrong-way risk. PD is
therefore not simply multiplied by fixed, independent numbers in a robust model.

**Example.** A lender has a 10 million loan with a 2% one-year PD and expects to
recover 60% of exposure after costs. The simplified expected loss is 80,000:
2% × 40% × 10 million. This does not mean the lender loses 80,000 each year. Most
outcomes have no default; a small set has a much larger loss. Expected loss is
the probability-weighted average used for pricing and provisioning, while
capital and limits address the distribution around it.

### Credit Assessment

Credit analysis asks whether a borrower can and will perform when payment is due,
and what the lender can recover if it does not. A valuable collateral mark is not
enough: cash-flow capacity, seniority, covenants, legal enforceability, correlation,
and stressed liquidation value determine the actual loss distribution.

Assessment considers:

- ability and willingness to pay;
- cash flow and leverage;
- business and industry risk;
- collateral and guarantees;
- legal ranking and covenants;
- currency and refinancing needs;
- country and transfer risk;
- concentration and correlation;
- recovery process.

### Concentration

Many individually acceptable loans can be dangerous together. Concentration can
arise from common:

- borrower or group;
- sector;
- geography;
- currency;
- collateral;
- technology;
- funding source;
- market factor.

Crypto exposures can share hidden concentration through the same stablecoin,
bridge, oracle, custodian, cloud provider, governance key, or liquidity venue.

Concentration analysis must look through legal names to common drivers. Lending
to five companies is not diversified if all five earn revenue from the same
protocol, hold the same collateral, and use the same custodian. It must also
compare position size with stressed exit capacity. Owning 5% of a small market
can create more liquidation risk than owning a larger nominal position in a deep
market.

| Credit concept | Question it answers | Common analytical error |
|---|---|---|
| PD | How likely is default over a stated horizon? | Treating a rating as timeless |
| EAD | How much will be owed when default occurs? | Ignoring future draws and market moves |
| LGD | What proportion is lost after recovery? | Using current collateral price without liquidation costs |
| Expected loss | What is the probability-weighted average loss? | Treating it as maximum or likely realized loss |
| Unexpected loss | How far can loss exceed the average? | Assuming diversification from borrower count alone |
| Concentration | Which exposures fail together? | Grouping only by legal entity or sector |

## Counterparty Credit Risk

Counterparty credit risk arises where exposure changes with market value before
final settlement, especially derivatives, securities financing, and unsettled
trades.

### Current And Potential Exposure

Counterparty exposure is asymmetric. If a derivative has negative value to a
bank, the bank owes the counterparty and does not currently lose from that
counterparty's default. If market prices reverse, the same trade may become a
positive replacement claim. Potential future exposure estimates that possible
increase over the close-out horizon.

- **current exposure:** positive replacement value today;
- **potential future exposure:** possible increase before close-out;
- **wrong-way risk:** exposure rises as the counterparty's credit quality falls.

An exchange owing assets to clients creates counterparty exposure even if the
client's displayed account balance is stable.

### Mitigation

Netting and collateral change the amount lost, but only if the legal and
operational machinery works during default. Close-out netting replaces many
positive and negative trades with one net claim under an enforceable agreement.
Variation margin pays current mark-to-market exposure; initial margin protects
against adverse movement between the last margin exchange and liquidation.
Haircuts protect against collateral price changes and liquidation costs.

- legal netting;
- variation and initial margin;
- eligible collateral and haircuts;
- central clearing;
- credit limits;
- diversification;
- frequent settlement;
- independent custody;
- termination and close-out rights.

Mitigation introduces residual risk. Collateral can fall in value, netting can
be unenforceable, margin can arrive late, and closing positions can move the
market.

**Example.** Two dealers have ten derivatives whose gross positive and negative
values are 120 million and 100 million. Without enforceable netting, the solvent
dealer may owe the full 100 million while recovering only a fraction of its
120 million claims in insolvency. With enforceable close-out netting, the
starting claim is 20 million before collateral. The economic difference comes
from legal enforceability, not arithmetic alone.

## Settlement Risk

Settlement risk is loss because a transaction fails to complete as expected.
It includes:

- **principal risk:** delivered one leg, did not receive the other;
- **replacement-cost risk:** must replace a failed trade at a worse price;
- **liquidity risk:** expected incoming funds do not arrive on time;
- **operational risk:** instructions or systems fail.

DvP and PvP reduce principal risk by conditioning one transfer on another. They
do not remove the risk of an unsound settlement asset, participant default
before settlement, or operational disruption.

Settlement exposure is shaped by timing and finality. A trade agreed today but
settled two days later creates replacement-cost exposure during that interval.
Once one leg becomes final, failure of the other creates principal exposure.
Netting reduces funding needs but concentrates obligations at a later settlement
point, so a default can create a larger liquidity shock for the surviving
participants.

## Market Risk

Market risk is loss from changes in prices or market variables:

- interest rates and yield curves;
- credit spreads;
- equity prices;
- foreign-exchange rates;
- commodity prices;
- implied volatility;
- correlations and basis relationships.

### Sensitivities

Sensitivity measures answer “what happens for a small movement in one risk
factor, holding others approximately constant?” Duration estimates a bond's
first-order response to yield; convexity improves the estimate for larger moves.
Option delta measures response to the underlying price, gamma describes how delta
changes, and vega measures response to implied volatility. These measures are
building blocks for hedging, not complete loss forecasts.

Risk can be approximated through local sensitivities:

- bond duration and convexity;
- option delta, gamma, vega, theta, and rho;
- FX delta;
- credit spread duration;
- key-rate duration;
- basis sensitivities.

Local sensitivities can fail under large, nonlinear, or discontinuous moves.

### Value At Risk

Value at Risk estimates a loss threshold over a horizon at a confidence level.
A one-day 99% VaR of 10 million means the model estimates that losses exceed 10
million on approximately 1% of modeled days—not that maximum loss is 10
million.

Methods include:

- historical simulation;
- parametric variance-covariance;
- Monte Carlo simulation.

VaR limitations include:

- little information about loss severity beyond the threshold;
- unstable correlations and volatility;
- inadequate history;
- model and data error;
- poor treatment of illiquidity and jumps;
- false precision.

### Expected Shortfall

Expected shortfall estimates average loss conditional on being beyond a chosen
quantile:

```text
ES_α = E[L | L ≥ VaR_α]
```

It better reflects tail severity but remains model-dependent.

VaR and expected shortfall aggregate many positions into a common loss measure,
but aggregation can conceal the underlying scenario. Two portfolios can have the
same VaR while one is exposed to frequent moderate losses and the other to a
rare discontinuous default. Risk managers therefore retain sensitivities,
concentrations, stress losses, and liquidity horizons alongside the aggregate
number.

| Measure | Primary use | What it does not show well |
|---|---|---|
| Position and notional | Scale and contractual amount | Net exposure or nonlinear payoff |
| Sensitivity | Local response to one factor | Large jumps and changing relationships |
| VaR | Quantile loss under modeled conditions | Severity beyond the quantile |
| Expected shortfall | Average modeled tail loss | Unmodeled scenarios and market liquidation |
| Stress loss | Impact of a specified adverse narrative | Probability of that narrative |
| Reverse stress | Conditions that break viability | Whether those conditions are likely |

## Interest-Rate Risk

Interest-rate risk affects both trading positions and the banking book.

- fixed-rate asset values fall as required yields rise;
- assets and liabilities reprice at different times;
- customers prepay loans or withdraw deposits differently from assumptions;
- yield curves change shape, not only level;
- hedges can create basis and optionality risk.

Economic-value measures estimate present-value effects. Earnings measures
estimate changes to net interest income over a horizon. Both are needed.

Three mechanisms deserve separate attention. **Gap risk** arises because assets
and liabilities reprice at different times or points on the yield curve.
**Basis risk** arises when similar instruments reference rates that do not move
together. **Option risk** arises when customers can change cash-flow timing—for
example, prepaying fixed-rate mortgages when rates fall or withdrawing deposits
when alternative yields rise.

Consider a bank funding ten-year fixed-rate loans with deposits that can reprice
quickly. If rates rise, deposit expense can increase before loan income does,
reducing near-term earnings. The present value of the fixed-rate loans also
falls, reducing economic value. Depositors may withdraw faster than the model
assumed, turning interest-rate risk into funding-liquidity risk.

## Liquidity Risk

### Funding Liquidity

The risk of being unable to meet obligations when due without unacceptable
loss.

Funding liquidity concerns the liability side and access to cash. A solvent firm
can fail if withdrawals, margin calls, or settlement obligations arrive before
it can monetize assets. Contractual maturity is only the starting point because
customers can behave differently under stress and lenders may refuse to renew.

### Market Liquidity

The risk of being unable to sell, hedge, or close a position near its observed
price.

Market liquidity is multidimensional. Tight quoted spreads do not guarantee
enough depth for a large trade; depth visible in an order book can disappear;
and the time needed to sell without moving price may lengthen during stress.
Valuation based on the last small trade can therefore materially exceed
recoverable value for a concentrated position.

### Intraday Liquidity

The risk of lacking funds or collateral at a specific moment during the day.

These interact:

```mermaid
flowchart TD
    Outflow["Withdrawals or margin calls"]
    Sale["Need to sell or finance assets"]
    Thin["Market depth is weak"]
    Discount["Large price concession"]
    Capital["Losses reduce capital and confidence"]
    More["Further funding outflows"]
    Outflow --> Sale --> Thin --> Discount --> Capital --> More --> Outflow
```

### Liquidity Measurements

No single ratio captures liquidity. Cash-flow ladders reveal timing mismatches,
survival horizons ask how long resources last without new funding, and
liquidation analysis estimates the amount and price at which assets can actually
be sold. Measurements should be produced by currency and legal entity because
cash trapped in one subsidiary or token cannot necessarily satisfy another's
obligation.

- contractual cash-flow ladder;
- expected and stressed outflows;
- survival horizon;
- liquid-asset buffer;
- funding concentration;
- asset encumbrance;
- collateral availability;
- liquidation horizon and price impact;
- intraday peak usage.

Stable historical behavior can reverse during a run. Operationally available
liquidity matters more than nominal asset value.

| Liquidity question | Relevant measure | Stress consideration |
|---|---|---|
| What must be paid and when? | Contractual and behavioral cash-flow ladder | Early withdrawals and margin calls |
| What cash is immediately usable? | Unencumbered liquid-asset buffer | Settlement location, currency, and operating hours |
| How long can the firm survive? | Survival horizon | No new unsecured funding |
| What can be sold? | Stressed liquidation value and horizon | Market depth and correlated sellers |
| Where is liquidity trapped? | Legal-entity and currency view | Transfer restrictions and cutoffs |
| What happens intraday? | Peak payment and collateral usage | Delayed incoming payments |

## Leverage Risk

Leverage uses borrowing, derivatives, or embedded structures to create exposure
larger than equity.

```text
Balance-sheet leverage
= (assets) / (equity)
```

If assets are 1,000 and equity is 50, a 5% asset loss eliminates equity before
considering income, hedging, or liability changes.

Derivatives can create large economic leverage with limited initial cash.
Gross notional alone can overstate risk, while net mark-to-market can understate
future exposure and liquidation cost.

## Operational Risk

Operational risk is loss from inadequate or failed processes, people, systems,
or external events. Examples include:

- incorrect trade or payment;
- software defect;
- access-control failure;
- fraud or insider abuse;
- third-party outage;
- failed model deployment;
- lost cryptographic keys;
- data corruption;
- legal-documentation error;
- natural disaster.

### Controls

Operational controls can be preventive, detective, or corrective. Segregation of
duties prevents one person from initiating and approving a payment.
Reconciliation detects a difference after records move. Backups and recovery
procedures restore service after failure. A resilient design uses all three
because no preventive control is perfect.

- segregation of duties;
- maker-checker approval;
- least privilege;
- reconciliations;
- change management;
- tested backups and recovery;
- dual control over keys and payments;
- incident response;
- vendor and dependency management;
- business continuity exercises.

Automation reduces manual error but can propagate a defect instantly and at
scale.

Operational-risk assessment commonly combines process mapping, risk and control
self-assessment, internal and external loss events, key risk indicators, and
scenario analysis. The aim is not only to count past incidents. Rare events may
be absent from internal history, while small recurring exceptions may expose a
control weakness capable of producing a much larger loss.

Operational resilience focuses on the service outcome. A payment provider maps
the people, systems, facilities, data, and third parties required to deliver a
critical payment service, defines a tolerable disruption, and tests whether the
service can remain within it under severe but plausible failures. Recovery of one
server is not enough if identity, telecommunications, or a cloud dependency
remains unavailable.

## Cyber Risk

Cyber risk overlaps operational risk but requires explicit threat analysis:

- credential theft;
- ransomware;
- supply-chain compromise;
- denial of service;
- data exfiltration;
- transaction manipulation;
- private-key compromise;
- smart-contract exploitation;
- insider misuse.

Risk management covers prevention, detection, containment, recovery, evidence,
notification, and learning. "Immutable" systems can preserve malicious
transactions as effectively as legitimate ones.

Cyber risk is often analyzed through a threat actor, attack path, vulnerable
asset, and business impact. This complements control checklists: strong encryption
does not stop an authorized administrator from being deceived into signing the
wrong transaction, and a patched application may still depend on a compromised
software package. The loss scenario must follow the attacker from initial access
to the financial or operational consequence.

## Model Risk

Model risk is adverse consequence from incorrect or misused models.

Sources include:

- conceptual error;
- incomplete variables;
- biased or poor-quality data;
- invalid extrapolation;
- implementation defects;
- parameter instability;
- use outside approved scope;
- human overreliance.

Model governance includes inventory, documentation, validation, change control,
performance monitoring, limitations, overrides, and accountable ownership.

Blockchain analytics risk scores, oracle prices, credit ratings, liquidation
models, and fraud systems are all models or model-like decision systems.

Validation asks three distinct questions. **Conceptual soundness** asks whether
the theory and assumptions fit the use. **Process verification** asks whether
data, code, and implementation reproduce the approved design. **Outcome
analysis** asks whether predictions remain accurate and stable in use. A model
can pass implementation tests yet fail because market behavior changed, or
predict well on average while performing poorly for a critical subgroup.

Model risk also depends on use. A noisy risk score used to prioritize manual
review may be acceptable; the same score used to freeze every customer above a
threshold can cause material conduct harm. Controls must therefore be
proportionate to the decision, reversibility, and consequence of error.

## Legal And Regulatory Risk

Legal risk includes:

- unenforceable contract;
- uncertain asset ownership;
- invalid collateral or netting;
- conflicting jurisdictions;
- insolvency recharacterization;
- breach of privacy, sanctions, securities, or consumer law;
- inadequate disclosure;
- lack of settlement finality.

Code execution does not settle legal characterization. A smart contract can
perform exactly as programmed while the resulting transfer breaches law or
fails to transfer the claimed offchain asset.

## Conduct And Reputational Risk

Conduct risk arises from unfair treatment, conflicts, manipulation,
mis-selling, misuse of information, or poor product governance. Reputation is
not merely public-relations sentiment: lost confidence can cause customer
outflows, higher funding costs, regulatory intervention, and employee loss.

## Strategic And Business Risk

A solvent, compliant product can still fail because:

- demand is insufficient;
- pricing does not cover costs;
- competitors change the market;
- technology becomes obsolete;
- regulation changes economics;
- concentration in one revenue source is excessive.

Business risk belongs in the same integrated framework because it affects
capital generation and viability.

## Systemic Risk

Systemic risk is disruption capable of impairing broad financial services or
the real economy.

Transmission channels include:

- common asset holdings;
- interbank and derivative exposures;
- payment and settlement dependencies;
- fire sales;
- runs;
- collateral and margin spirals;
- critical service providers;
- confidence and information contagion.

A protocol can be systemically important within DeFi even if it is small
relative to global banking. Importance depends on the system boundary and
dependencies being analyzed.

Systemic risk contains feedback. A bank sells assets to meet withdrawals; the
sale lowers market prices; lower prices create losses and margin calls at other
firms; those firms sell too. Individually rational risk reduction becomes
collectively destabilizing. Macroprudential analysis therefore considers common
exposures, interconnectedness, substitutability of critical services, and the
procyclical effect of margins, haircuts, and credit supply.

## Hedging

A hedge offsets exposure with another position.

### Basis Risk

Hedge and exposure may not move identically because of:

- different instruments or maturities;
- location or grade;
- collateral and funding;
- liquidity;
- index composition;
- timing;
- counterparty credit.

### Dynamic Hedging

Option and nonlinear exposures require rebalancing as markets move. Transaction
costs, gaps, liquidity, and volatility can make theoretical replication
inexact.

### Hedge Accounting Versus Economic Hedging

An economically sound hedge can produce accounting volatility if recognition
and measurement differ. Hedge accounting has specific qualification,
documentation, and effectiveness rules; it does not determine whether economic
risk is genuinely reduced.

## Stress Testing

Stress testing asks how positions and the institution behave under severe
conditions.

### Types

- **sensitivity:** changes one or a few variables;
- **historical scenario:** replays a past event;
- **hypothetical scenario:** constructs a plausible future shock;
- **reverse stress:** asks what would make the business model fail;
- **system-wide stress:** includes feedback between institutions and markets.

### Good Scenario Design

A scenario should be:

- severe enough to challenge the business;
- internally coherent;
- broad enough to capture interacting risks;
- explicit about time horizon and management actions;
- updated for new products and vulnerabilities;
- skeptical about market liquidity and correlations.

For digital assets, a coherent scenario might combine:

- stablecoin depeg;
- exchange and bridge withdrawal suspension;
- collateral-price fall;
- oracle delay;
- higher blockchain fees;
- validator or sequencer outage;
- counterparty failure;
- legal freeze;
- customer run.

A list of shocks is not yet a scenario. The narrative should explain causality
and timing. A stablecoin depeg can reduce collateral value, cause liquidations,
increase chain congestion, delay oracle updates, and trigger withdrawal
suspensions at a counterparty. Each second-round effect changes the next, and
management actions must use prices and liquidity available at that stage.

**Worked example.** Assume a platform holds 100 million of a token that normally
trades 200 million per day. A stress test should not simply apply a 30% price
fall. It should estimate how much volume is genuine and accessible, how the
platform's own sale changes price, whether collateral haircuts increase, which
counterparties demand margin, and whether customers withdraw simultaneously.
The useful output is a time path of liquidity and capital, not one static loss.

### Management Actions

Stress tests often assume asset sales, hedges, capital raising, or liquidity
facilities. Those actions must be feasible under the same stressed conditions.
Every participant cannot sell the same asset at the unstressed price.

## Risk-Adjusted Return

Raw revenue is not sufficient. Economic evaluation considers:

```text
Risk-adjusted return
= (return - expected loss - costs) / capital or risk measure
```

Implementation varies, but the principle is consistent: revenue earned by
taking unpriced tail, liquidity, legal, or operational risk is not necessarily
economic profit.

## The Three-Lines Model

A common governance arrangement distinguishes:

1. **business and operations:** own and manage risks;
2. **independent risk and compliance:** set frameworks, advise, monitor, and
   challenge;
3. **internal audit:** independently assesses governance and controls.

Boards oversee risk appetite and senior management. External audit, regulators,
and supervisors provide additional assurance or oversight but do not replace
internal accountability.

The model fails if the second line designs the business's controls for it, if
the first line treats risk as an approval department, or if audit becomes a
continuous operational control.

## Risk Data And Aggregation

Risk decisions depend on knowing total exposure. Data must map:

- legal entity;
- customer and beneficial owner;
- counterparty group;
- instrument and underlying;
- currency and maturity;
- collateral and guarantor;
- venue, custodian, wallet, and protocol;
- risk factor;
- jurisdiction.

Duplicate identifiers, stale prices, missing derivatives, and inconsistent
netting can make an apparently precise risk report materially wrong.

Aggregation requires common identifiers and explicit relationships. A parent and
subsidiary may be separate legal counterparties but one economic group. A
derivative can reference an issuer without being recorded as that issuer's cash
security. Wrapped assets on several chains can all depend on one reserve.
Risk-data architecture must preserve these many-to-many links rather than force
every exposure into one flat product hierarchy.

Timeliness is part of accuracy. A complete exposure report delivered after a
market closes or a bridge is drained cannot support the decision it was designed
for. Institutions therefore define data lineage, reconciliation, quality
thresholds, and escalation for missing or stale inputs, rather than silently
substituting the last available value.

## Early-Warning Indicators

Indicators can include:

- limit usage and breaches;
- credit downgrades and spread widening;
- collateral disputes;
- deposit and funding outflows;
- market depth and haircut changes;
- settlement failures;
- operational incidents;
- unusual customer behavior;
- vendor service degradation;
- governance or key changes;
- oracle deviation and protocol utilization;
- audit findings and overdue remediation.

An indicator needs thresholds, ownership, escalation, and action. A dashboard
without response rules is observation, not control.

## Failure Analysis

Separate:

1. **trigger:** the event that begins visible failure;
2. **vulnerability:** condition that made the system fragile;
3. **transmission:** how losses or disruption spread;
4. **control failure:** why prevention or containment failed;
5. **impact:** financial, customer, legal, and systemic consequences;
6. **recovery:** liquidity, recapitalization, resolution, or technical response;
7. **lesson:** specific change supported by evidence.

Calling a price fall "the cause" can miss leverage, maturity mismatch,
concentration, governance, and inaccurate records that made the fall fatal.

## Analytical Checklist

For any product, protocol, company, or portfolio:

1. What economic exposure is being accepted?
2. Which legal entities and counterparties bear it?
3. How is it measured under normal and stressed conditions?
4. Which concentrations and common dependencies exist?
5. What capital and liquidity absorb loss?
6. Which limits prevent excessive exposure?
7. What collateral, netting, insurance, or hedge mitigates it?
8. What residual and basis risk remains?
9. Which models and data drive decisions?
10. What operational and cyber failures are plausible?
11. What legal and conduct obligations apply?
12. How quickly can exposure be reduced?
13. What feedback loops arise during stress?
14. Who owns escalation and recovery?
15. What would make the activity non-viable?

## Connections

- [Money, Banking, And Balance Sheets](../01-money-banking-and-payments/money-banking-and-balance-sheets.md)
  distinguishes capital, liquidity, and solvency.
- [Securities And Financial Instruments](../02-financial-markets/securities-and-financial-instruments.md)
  explains the contracts creating financial exposure.
- [Financial Regulation, Compliance, And Accounting](financial-regulation-compliance-and-accounting.md)
  explains prudential and conduct frameworks.
- [DeFi Risk, Security, And Economic Attacks](../../04-decentralized-finance/04-defi-risk-and-failures/defi-risk-security-and-economic-attacks.md)
  applies integrated risk analysis to protocols.

## References

- Basel Committee on Banking Supervision,
  [Core Principles for effective banking supervision](https://www.bis.org/basel_framework/chapter/BCP/40.htm)
- Basel Committee on Banking Supervision,
  [General credit risk management](https://www.bis.org/basel_consolidated_guidelines/chapter/CRI/10.htm)
- Basel Committee on Banking Supervision,
  [Liquidity risk management and supervision](https://www.bis.org/basel_consolidated_guidelines/chapter/LQY/10.htm)
- Basel Committee on Banking Supervision,
  [Stress testing](https://www.bis.org/basel_consolidated_guidelines/chapter/RMA/30.htm)
- Basel Committee on Banking Supervision,
  [Counterparty credit risk](https://www.bis.org/basel_framework/chapter/SRP/32.htm)
- Basel Committee on Banking Supervision,
  [Principles for effective risk data aggregation and risk reporting](https://www.bis.org/publ/bcbs239.htm)
- Committee of Sponsoring Organizations of the Treadway Commission,
  [Enterprise Risk Management](https://www.coso.org/enterprise-risk-management)
- Institute of Internal Auditors,
  [The IIA's Three Lines Model](https://www.theiia.org/en/content/position-papers/2020/the-iias-three-lines-model-an-update-of-the-three-lines-of-defense/)
- Basel Committee on Banking Supervision,
  [Interest rate risk in the banking book](https://www.bis.org/basel_framework/chapter/SRP/31.htm)
- Basel Committee on Banking Supervision,
  [Minimum capital requirements for market risk](https://www.bis.org/bcbs/publ/d457.htm)
- Basel Committee on Banking Supervision,
  [Principles for the sound management of operational risk](https://www.bis.org/bcbs/publ/d515.htm)
- Basel Committee on Banking Supervision,
  [Principles for operational resilience](https://www.bis.org/bcbs/publ/d516.htm)
