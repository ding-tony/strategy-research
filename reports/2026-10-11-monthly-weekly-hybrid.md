# Monthly core plus different-selection weekly slot

Period: 2022-02-07–2026-10-02. Initial capital: $3,000. No lab changes.

| Strategy | End value | Total return | CAGR | Ann. volatility | Sharpe | Max drawdown | Orders |
|---|---:|---:|---:|---:|---:|---:|---:|
| 100% current monthly | $84,881.07 | 2729.37% | 105.24% | 42.81% | 1.899 | -35.84% | 172 |
| 80% monthly + 20% cash | $47,055.89 | 1468.53% | 80.78% | 34.54% | 1.893 | -29.89% | 167 |
| 80% monthly + 20% weekly/cash | $63,050.77 | 2001.69% | 92.53% | 35.82% | 2.015 | -29.52% | 240 |

## Interpretation

The hybrid improves in-sample Sharpe and drawdown versus fully invested monthly, but ends with 25.72% less wealth. Against monthly-plus-cash it adds $15,994.88, or 33.99% more terminal wealth, with 1.29 percentage points more volatility and slightly less drawdown. Much of the risk reduction relative to full monthly is therefore attributable to the lower core allocation/cash reserve; the weekly slot adds return and Sharpe versus that control.

The weekly slot is invested on 591 of 1,168 trading days (50.60%); average total cash is 10.11%. There are 242 raw simulated trades, 240 after same-price netting. The monthly-only baseline has 174 raw / 172 net. Across 57 calendar months, including partial endpoint months, the hybrid averages 4.21 net orders and exceeds five in 16 months, with 32 orders above those monthly allowances. Cost estimates are not applied.

It does not establish independent diversification: the largest observed combined sector exposure is 87.35%, and the largest stock weight reaches 50.13%. The 29.52% maximum drawdown remains substantial. Historical earnings coverage is missing or expired during some weekly holdings for ALL, APA, BKR, CNC, FICO, JBL, NRG, TPR, TRGP, TTWO and VRSN. Results are shareable with caveats, not qualification evidence or a reason to change live labs.

## Execution and exposure

| Strategy | Average cash | Weekly invested days | Orders/month | Months >5 orders | Extra orders beyond five | Largest stock weight | Largest sector weight |
|---|---:|---:|---:|---:|---:|---:|---:|
| monthlyOnly | 0.63% | 0.00% | 3.02 | 1 | 1 | 60.29% | 88.47% |
| monthlyCash | 19.80% | 0.00% | 2.93 | 1 | 1 | 49.90% | 75.27% |
| hybrid | 10.11% | 50.60% | 4.21 | 16 | 32 | 50.13% | 87.35% |

## Method and validation

- Same archive 2022-02-07 through 2026-10-02, $3000 total, no external contributions. Research only, active labs unchanged.
- Frozen conservative monthly and sector-cap weekly selected baskets. Monthly rank weights 50/33.3/16.7 inside core; sector cap 2 in source baskets. Hybrid combined sector exposure is measured, not newly capped.
- Monthly target budget 80% core / 20% weekly or cash, reset only at archived monthly review. $100 ordinary-adjustment minimum may leave small allocation deviations; full departures and stops sell regardless of minimum.
- Weekly slot holds at most one highest-ranked eligible weekly-selected stock absent from monthly selected basket; retain while eligible, rotate only when it leaves weekly basket or enters monthly. No deeper ranking search, no weekly weight adjustment, no 50% trigger.
- Monthly stop 25% from latest monthly opening reference, confirmed daily close, next-session open exit. Stop proceeds remain earmarked core cash until next monthly review. Weekly slot has existing earnings exit but no 25% stop.
- Weekly earnings eligibility/close exit uses existing backtest SQLite report dates and production weekday check; excludes next-business-day earnings entry. Historical knowability/coverage incomplete and holiday-edge limitations remain.
- Whole-account 85%-of-starting-capital floor: daily-close breach exits all next session open, pauses. No intra-day floor model. Cash earns zero.
- Monthly and weekly decisions use archived prior-session selections; monthly dates are first weekly review of month, not always calendar first trading day. Source selection buffers frozen, not reranked following hybrid exits.
- One global cash ledger, common adjusted market prices, archived monthly fill overrides, net same-price opposite orders. No fees, spreads, slippage, tax, FX. Current-universe survivorship/incomplete fundamentals bias; previously examined in-sample history, no out-of-sample proof.
- Orders are netted by session, ticker and identical fill price. Raw simulated trade counts are also preserved. Monthly-only has 174 raw trades / 172 net orders because two same-open stop/re-entry pairs offset; no claim that a broker automatically nets submitted orders.
- Validated all daily cash/NAV from net orders, attribution to terminal P&L, no duplicate slot/core names, earmarked cash, and exact prior monthly stop baseline trades/value/Sharpe. Sharpe is arithmetic daily sample return, zero risk-free, sqrt(252).

Supporting results: [data/2026-10-11-monthly-weekly-hybrid.json](data/2026-10-11-monthly-weekly-hybrid.json).
