# October-2 aligned replay: monthly stock stop 20 25 comparison

Period: 2026-08-03–2026-10-02. Starting capital: $3,000. Research only; no lab changes.

| Variant | Ending value | Return | Annual volatility | Sharpe | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|
| baseline | $4,090.42 | 36.35% | 56.64% | 3.423 | -15.03% | 9 |
| stockStop25 | $4,090.42 | 36.35% | 56.64% | 3.423 | -15.03% | 9 |
| stockStop20 | $4,090.42 | 36.35% | 56.64% | 3.423 | -15.03% | 9 |

## Winner breadth

| Variant | Closed-position win rate | Top-three positive-profit share | Stock-stop exits | Months >5 trades |
|---|---:|---:|---:|---:|---:|
| baseline | 66.67% | 92.63% | 0 | 1 |
| stockStop25 | 66.67% | 92.63% | 0 | 1 |
| stockStop20 | 66.67% | 92.63% | 0 | 1 |

## Full-history results (already October-2 aligned, unchanged)

| Variant | Ending value | Return | Annual volatility | Sharpe | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|
| baseline | $79,690.12 | 2556.34% | 43.69% | 1.838 | -38.82% | 170 |
| stockStop25 | $84,881.07 | 2729.37% | 42.81% | 1.899 | -35.84% | 174 |
| stockStop20 | $67,697.17 | 2156.57% | 41.54% | 1.828 | -35.70% | 175 |

## Method and validation

- Common cutoff 2026-10-02; saved October-9 replay curves and transactions truncated to the exact October-2 session. All returns, volatility, Sharpe, drawdown, CAGR, trade counts and profit attribution recomputed; no relabeling of October-9 metrics. Two monthly reviews and 44 daily observations.
- Raw cached daily closes and original recorded opening fills retained. Daily cash/quantities/NAV independently reconstructed and reconciled to every saved prefix observation; open-position P&L marked on October 2. No October-5 trades, October-9 terminal overrides or future exits included.
- Strategy settings are unchanged from the source study. Start date remains August 3, 2026, so these short lab replays must not be ranked directly against full-history tests.
- Frozen monthly rank-ordered selections and dates from archived backtest / current lab. No re-ranking after early exits; isolates execution and cash drag, not changed retention-buffer selections.
- Rank weights 50/33.3/16.7, sector cap max two, $100 minimum normal adjustments. No 50% trigger and no earnings exit.
- Stop reference resets at each monthly rebalance open. Daily close <=75% (25% stop) or <=80% (20% stop) triggers full exit at next actual session open, regardless of $100 minimum. Hold cash until next monthly review, when the same stock may be selected again.
- All variants model portfolio floor at 85% of initial capital: daily-close breach sells all at next open and pauses without automatic restart. This is a close-to-next-open model, not an intraday reproduction of live monitoring.
- Archive uses current-universe selection: survivorship bias, incomplete historical fundamentals/coverage. This previously examined sample is not independent out-of-sample validation.
- Volatility and zero-risk-free Sharpe from daily sample returns with sqrt(252); initial capital prepended. Terminal positions marked, not liquidated.
- Validation: baseline recorded trades reproduced, all daily cash/NAV independently reconstructed, attribution reconciled, thresholds and next-session timing asserted, live labs unchanged.
- Short-sample annualized statistics are not reliable forecasts. Original October-9 reports remain untouched. All active labs unchanged.
- The unchanged full-history stop comparison also covers February 7, 2022–October 2, 2026, with adjusted historical fills, frozen selections, $100 monthly adjustments, sector count cap two and 85% initial-capital floor. Both evidence windows are included separately.

Supporting comparator metrics: [data/2026-10-11-monthly-stock-stop-20-25-comparison.json](data/2026-10-11-monthly-stock-stop-20-25-comparison.json). This public extract contains saved rules and metrics, not raw simulation ledgers.
Original reports are retained. Reproduce with `python3 scripts/align_strategy_comparator_cutoff.py`.
