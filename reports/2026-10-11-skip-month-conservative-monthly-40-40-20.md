# Skip-month conservative monthly: 40/40/20 weights

Period: 2022-02-07–2026-10-02. Initial capital: $3,000. Research only; no lab changes.

Skip-month ends with 14.71% more wealth than the saved normal 40/40/20 reference, but volatility rises 2.19 percentage points and Sharpe changes by -0.011. Drawdown is almost unchanged. It is a higher-return alternative, not a new highest-Sharpe result.

On exactly matched eligibility, skip-month ends with 20.07% more wealth; Sharpe changes only +0.001. Return improves without a meaningful observed risk-adjusted advantage. No statistical significance is established.

| Strategy | Ending value | Total return | CAGR | Volatility | Sharpe | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|---:|
| Normal conservative 40/40/20 (reference) | $81,354.37 | 2611.81% | 103.38% | 41.44% | 1.926 | -36.41% | 172 |
| Normal conservative 40/40/20 (matched eligibility) | $77,720.47 | 2490.68% | 101.39% | 41.11% | 1.914 | -36.41% | 173 |
| Skip-month conservative 40/40/20 | $93,321.70 | 3010.72% | 109.47% | 43.63% | 1.915 | -36.38% | 173 |
| Normal conservative 50/33/17 (baseline check) | $84,881.07 | 2729.37% | 105.24% | 42.81% | 1.899 | -35.84% | 174 |
| Skip-month conservative 50/33/17 (baseline check) | $93,765.38 | 3025.51% | 109.68% | 44.00% | 1.906 | -35.95% | 180 |

## Breadth and execution

| Strategy | Closed-position win rate | Top-three positive-profit share | Stop exits | Months >5 trades |
|---|---:|---:|---:|---:|
| Normal conservative 40/40/20 (reference) | 62.50% | 67.20% | 4 | 1 |
| Normal conservative 40/40/20 (matched eligibility) | 61.22% | 66.97% | 4 | 1 |
| Skip-month conservative 40/40/20 | 62.79% | 71.60% | 4 | 2 |
| Normal conservative 50/33/17 (baseline check) | 62.50% | 68.15% | 4 | 1 |
| Skip-month conservative 50/33/17 (baseline check) | 60.47% | 73.26% | 4 | 2 |

## Calendar-year returns (2022 and 2026 partial)

| Strategy | 2022 | 2023 | 2024 | 2025 | 2026 |
|---|---:|---:|---:|---:|---:|
| Normal conservative 40/40/20 (reference) | 2.80% | 40.83% | 340.98% | 47.98% | 187.06% |
| Normal conservative 40/40/20 (matched eligibility) | 2.80% | 40.83% | 340.98% | 47.98% | 174.23% |
| Skip-month conservative 40/40/20 | 10.19% | 25.34% | 335.20% | 48.32% | 248.92% |

## Method and validation

- 2022-02-07 through 2026-10-02; $3,000 initial capital; three stocks; monthly full weight maintenance; 40/40/20 entry and monthly target weights; sector count cap two; retention buffer one; $100 ordinary adjustment minimum; 25% daily-close stock stop, next-session open exit; 85%-initial-capital close-to-next-open portfolio floor. No earnings exits or 50% concentration trigger.
- Reuse validated monthly conservative selection schedules and prior-session ranking audit from 2026-10-11-skip-month-conservative-monthly. Score adds ascending momentum rank to ascending negative asset-growth rank using SEC facts filed before signal date. Skip-month uses a 252-session return ending 21 sessions before signal. Normal uses the return ending at signal.
- normal40 exactly reproduces the highest-Sharpe saved strategy. normalMatched40 and skip40 share eligibility and differ only in momentum input. Seven reviews exclude otherwise eligible stocks with insufficient cached skip-month history; not all exclusions are recent listings.
- Monthly dates are the archived first weekly review session in each month, not always the exact first trading day. Frozen no-stop selection schedules preserve the existing reference methodology; stocks are not dynamically reranked after stops. Upgrade to dynamic retention before deployment.
- Dividend-adjusted cached OHLC with the same archived monthly fill overrides applied to all variants; SATS/ECHO history stitched June 24, 2026. Current cached universe and sector labels: survivorship and incomplete historical fundamental coverage biases. No costs, slippage, FX, taxes or cash interest.
- Sharpe and volatility use sample daily arithmetic returns including initial capital, zero risk-free rate, sqrt(252). Three archived baselines reproduced trade-for-trade. Independent daily cash/NAV and position-episode profit reconciled; initial allocations and stop timing checked. All live lab files unchanged.
- In-sample weight/momentum sensitivity, not independent validation or evidence of statistical significance. Calendar years 2022 and 2026 are partial.

Validation: share with caveats. Historical selection and coverage limitations prevent a deployment-grade or causal claim.

Supporting comparator metrics: [data/2026-10-11-skip-month-conservative-monthly-40-40-20.json](data/2026-10-11-skip-month-conservative-monthly-40-40-20.json). This public extract contains saved rules and metrics, not raw simulation ledgers.
Reproduce with `python3 scripts/backtest_skip_month_conservative_40_40_20.py` using the local cached research inputs.
