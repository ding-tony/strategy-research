# Skip-month plus conservative factor: matched monthly backtest

Period: 2022-02-07–2026-10-02. Initial capital: $3,000. Research only; no lab changes.

With the current 25% monthly stop, skip-month plus the conservative factor ends at $93,765 versus $81,746 for normal momentum on the identical eligible pool: 14.70% more ending wealth. Volatility rises from 42.52% to 44.00%, Sharpe improves slightly from 1.890 to 1.906, and maximum drawdown is essentially unchanged. Compared with the actual current strategy's full eligibility, ending wealth is 10.47% higher ($84,881 baseline).

This is promising but not a clear risk-adjusted upgrade: the Sharpe difference is small and top-three positive-profit concentration increases from 67.57% to 73.26%. No statistical significance or out-of-sample superiority is established.

| Strategy | End value | Return | CAGR | Volatility | Sharpe | Max drawdown | Orders | Stops |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Current conservative, no stop | $79,690.12 | 2556.34% | 102.48% | 43.69% | 1.838 | -38.82% | 170 | 0 |
| Current conservative, 25% stop | $84,881.07 | 2729.37% | 105.24% | 42.81% | 1.899 | -35.84% | 174 | 4 |
| Normal + conservative, matched pool, no stop | $76,746.41 | 2458.21% | 100.84% | 43.40% | 1.829 | -38.82% | 171 | 0 |
| Normal + conservative, matched pool, 25% stop | $81,745.61 | 2624.85% | 103.59% | 42.52% | 1.890 | -35.84% | 175 | 4 |
| Skip-month + conservative, matched pool, no stop | $88,075.53 | 2835.85% | 106.88% | 44.85% | 1.848 | -38.82% | 175 | 0 |
| Skip-month + conservative, matched pool, 25% stop | $93,765.38 | 3025.51% | 109.68% | 44.00% | 1.906 | -35.95% | 180 | 4 |

## Winner breadth

| Strategy | Closed-position win rate | Largest winner share | Top-three profit share | Distinct stocks |
|---|---:|---:|---:|---:|
| current | 63.64% | 27.93% | 66.59% | 37 |
| currentStop25 | 62.50% | 28.85% | 68.15% | 37 |
| matchedCurrent | 62.22% | 28.52% | 65.98% | 37 |
| matchedCurrentStop25 | 61.22% | 27.71% | 67.57% | 37 |
| skipMonth | 58.97% | 30.36% | 71.91% | 37 |
| skipMonthStop25 | 60.47% | 30.35% | 73.26% | 37 |

Different stock selections: 20 of 56 monthly reviews.

Seven reviews exclude otherwise eligible stocks with insufficient cached skip-month history. This includes SNDK in March 2026 and several older companies with short cache coverage in January/February 2025; the exclusions are not all recent listings. The supporting JSON records every exclusion. Both matched variants use the same exclusions, while the actual current reference keeps its original eligibility.

## Method and validation

- Same 2022-02-07 to 2026-10-02 archive period, $3000, 3 stocks, rank weights 50/33.3/16.7, sector count cap 2, retention buffer 1, $100 minimum ordinary adjustments, monthly weight maintenance. No earnings exit or 50% concentration trigger.
- The matched variants start with the same normal top-300 trailing-dollar-liquidity pool and SEC investment scores, then symmetrically remove stocks lacking skip-month history. Momentum ranks are computed over this common liquidity pool. Score is ascending momentum rank plus ascending negative asset-growth rank. Only the momentum factor changes in the matched pair. Current/currentStop25 separately retain the complete original eligibility; fresh normal selections reproduce all archived baskets. SEC facts require filing strictly before the signal date. This factor favors conservative asset growth, not general valuation/profitability.
- Monthly dates are the archived first weekly review session in each month, not always the exact first trading day. Sector cap limits stock count, not sector dollar weight.
- Paired stop comparisons freeze each no-stop target schedule, matching the earlier monthly stop study. This isolates execution; it does not rerank retention after stop exits.
- Existing skip-month formula is a 252-session return ending 21 sessions before the signal, not a newly defined canonical academic 12-1 signal.
- 25% close-confirmed stop uses production implementation; next-session-open full exit, cash until monthly review. Fixed 85% starting-capital floor is daily-close-to-next-open; no interest.
- Synthetic dividend-adjusted prices and previously recorded monthly fills, no fees/spread/slippage/FX/tax. Current cached universe, not complete dated membership: survivorship and incomplete fundamental-availability biases. Previously examined in-sample period, not independent validation.
- Sharpe uses sample daily arithmetic returns, zero risk-free rate, sqrt(252). Independently reconciled cash/NAV and episode P&L; prior baseline and stop study reproduced. All active labs unchanged.

Supporting results: [data/2026-10-11-skip-month-conservative-monthly.json](data/2026-10-11-skip-month-conservative-monthly.json).
