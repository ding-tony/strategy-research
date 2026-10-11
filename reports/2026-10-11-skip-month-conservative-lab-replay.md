# Skip-month plus conservative: current monthly lab replay

Period: 2026-08-03–2026-10-09. Starting capital: $3,000. No lab changes.

| Strategy | End value | Return | Ann. volatility | Sharpe | Max drawdown | Orders | Stops |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Current lab, recorded selections | $4,502.46 | 50.08% | 56.71% | 3.975 | -15.03% | 13 | 0 |
| Normal + conservative, recalculated | $4,380.93 | 46.03% | 57.39% | 3.688 | -15.03% | 11 | 0 |
| Skip-month + conservative monthly | $5,391.35 | 79.71% | 83.08% | 4.033 | -14.85% | 10 | 0 |

## Selections (rank order: 50%, 33.3%, 16.7%)

| Review | Current lab | Normal recalculated | Skip-month + conservative |
|---|---|---|---|
| 2026-08-03 | WDC, SNDK, CNC | WDC, SNDK, CNC | WDC, SNDK, MRNA |
| 2026-09-08 | MRNA, VLO, WBD | MRNA, VLO, WDC | MRNA, VLO, WDC |
| 2026-10-05 | MRNA, VLO, ON | MRNA, VLO, WDC | MRNA, VLO, WDC |

## Trades

| Strategy | Date | Side | Stock | Amount | Reason |
|---|---|---|---|---:|---|
| Current lab, recorded selections | 2026-08-03 | BUY | WDC | $1,500.00 | weekly_rebalance |
| Current lab, recorded selections | 2026-08-03 | BUY | SNDK | $1,000.00 | weekly_rebalance |
| Current lab, recorded selections | 2026-08-03 | BUY | CNC | $500.00 | weekly_rebalance |
| Current lab, recorded selections | 2026-09-08 | SELL | WDC | $1,371.53 | not_in_target |
| Current lab, recorded selections | 2026-09-08 | SELL | SNDK | $1,525.58 | not_in_target |
| Current lab, recorded selections | 2026-09-08 | SELL | CNC | $534.93 | not_in_target |
| Current lab, recorded selections | 2026-09-08 | BUY | MRNA | $1,716.02 | weekly_rebalance |
| Current lab, recorded selections | 2026-09-08 | BUY | VLO | $1,144.01 | weekly_rebalance |
| Current lab, recorded selections | 2026-09-08 | BUY | WBD | $572.01 | weekly_rebalance |
| Current lab, recorded selections | 2026-10-05 | SELL | WBD | $627.12 | not_in_target |
| Current lab, recorded selections | 2026-10-05 | SELL | MRNA | $204.97 | weekly_rebalance |
| Current lab, recorded selections | 2026-10-05 | BUY | VLO | $148.64 | weekly_rebalance |
| Current lab, recorded selections | 2026-10-05 | BUY | ON | $683.45 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-08-03 | BUY | WDC | $1,500.00 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-08-03 | BUY | SNDK | $1,000.00 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-08-03 | BUY | CNC | $500.00 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-09-08 | SELL | SNDK | $1,525.58 | not_in_target |
| Normal + conservative, recalculated | 2026-09-08 | SELL | CNC | $534.93 | not_in_target |
| Normal + conservative, recalculated | 2026-09-08 | BUY | MRNA | $1,716.02 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-09-08 | BUY | VLO | $1,144.01 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-09-08 | SELL | WDC | $799.52 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-10-05 | SELL | MRNA | $261.73 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-10-05 | BUY | VLO | $110.80 | weekly_rebalance |
| Normal + conservative, recalculated | 2026-10-05 | BUY | WDC | $150.93 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-08-03 | BUY | WDC | $1,500.00 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-08-03 | BUY | SNDK | $1,000.00 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-08-03 | BUY | MRNA | $500.00 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-09-08 | SELL | SNDK | $1,525.58 | not_in_target |
| Skip-month + conservative monthly | 2026-09-08 | BUY | MRNA | $785.31 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-09-08 | BUY | VLO | $1,407.87 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-09-08 | SELL | WDC | $667.60 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-10-05 | SELL | MRNA | $322.09 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-10-05 | BUY | VLO | $136.36 | weekly_rebalance |
| Skip-month + conservative monthly | 2026-10-05 | BUY | WDC | $185.74 | weekly_rebalance |

## Method and validation

- August 3–October 9, 2026, $3000 starting capital, same recorded monthly review dates. Research only; all live lab files verified unchanged.
- Both use monthly rank weights 50/33.333/16.667, sector count cap 2, retention buffer 1, $100 ordinary adjustment minimum, daily-close-confirmed 25% stock stop with next-session-open exit, fixed 85% initial-capital floor. No earnings exit or 50% concentration trigger.
- Current uses recorded live-lab baskets. FreshCurrent and skipConservative recompute normal versus skip-month momentum using identical cached histories, top-300 liquidity pool and SEC negative-asset-growth ranks. This third control separates signal changes from differences between recorded live selections and refreshed historical inputs. All pool stocks have skip-month history in this period; SEC filing dates strictly precede signal dates.
- Raw historical execution bars, baseline recorded fills and previously verified terminal closes; other stocks use cached daily opens/closes. Momentum uses adjusted closes as production does. All signals use prior-session data; retention is based on each replay portfolio.
- Current baseline reproduces every prior verified trade, value and Sharpe. Both independently reconcile daily cash/NAV, position quantities and episode P&L. Stops use the production execution path.
- Only three monthly reviews, no out-of-sample validation or statistical significance. No fees/spread/slippage/FX/taxes or interest. Current cached universe, not a historical-membership rerun; the result does not establish future performance.

Supporting comparator metrics: [data/2026-10-11-skip-month-conservative-lab-replay.json](data/2026-10-11-skip-month-conservative-lab-replay.json). This public extract contains saved rules and metrics, not raw simulation ledgers.
