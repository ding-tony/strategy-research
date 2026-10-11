# Monthly rank-weight: 20% versus 25% single-stock stop

Research only; no live lab changes.

## fullHistory: 2022-02-07–2026-10-02

| Variant | Total return | Annual volatility | Sharpe | Max drawdown | Orders | Stops |
|---|---:|---:|---:|---:|---:|---:|
| baseline | 2556.34% | 43.69% | 1.838 | -38.82% | 170 | 0 |
| stockStop25 | 2729.37% | 42.81% | 1.899 | -35.84% | 174 | 4 |
| stockStop20 | 2156.57% | 41.54% | 1.828 | -35.70% | 175 | 7 |

### Stop events

| Stock | Signal close | Exit open | Loss from monthly reference | Return after exit to next review |
|---|---|---|---:|---:|
| BKR (stockStop25) | 2022-06-24 | 2022-06-27 | -23.21% | -3.74% |
| DELL (stockStop25) | 2024-08-02 | 2024-08-05 | -33.96% | 0.00% |
| CVNA (stockStop25) | 2025-01-03 | 2025-01-06 | -28.16% | 0.00% |
| SNDK (stockStop25) | 2026-07-17 | 2026-07-20 | -22.96% | -17.67% |
| BKR (stockStop20) | 2022-06-16 | 2022-06-17 | -21.24% | -6.15% |
| OXY (stockStop20) | 2022-06-17 | 2022-06-21 | -17.23% | 1.99% |
| CVNA (stockStop20) | 2024-04-15 | 2024-04-16 | -21.31% | 80.35% |
| DELL (stockStop20) | 2024-07-30 | 2024-07-31 | -16.24% | -21.16% |
| CVNA (stockStop20) | 2024-12-31 | 2025-01-02 | -23.29% | -6.35% |
| NRG (stockStop20) | 2025-03-10 | 2025-03-11 | -20.53% | -5.05% |
| SNDK (stockStop20) | 2026-07-16 | 2026-07-17 | -25.34% | -15.04% |

Portfolio-floor events: {"baseline": [], "stockStop25": [], "stockStop20": []}

## labPeriod: 2026-08-03–2026-10-09

| Variant | Total return | Annual volatility | Sharpe | Max drawdown | Orders | Stops |
|---|---:|---:|---:|---:|---:|---:|
| baseline | 50.08% | 56.71% | 3.975 | -15.03% | 13 | 0 |
| stockStop25 | 50.08% | 56.71% | 3.975 | -15.03% | 13 | 0 |
| stockStop20 | 50.08% | 56.71% | 3.975 | -15.03% | 13 | 0 |

### Stop events

| Stock | Signal close | Exit open | Loss from monthly reference | Return after exit to next review |
|---|---|---|---:|---:|

Portfolio-floor events: {"baseline": [], "stockStop25": [], "stockStop20": []}

## Method and limitations

- Frozen monthly rank-ordered selections and dates from archived backtest / current lab. No re-ranking after early exits; isolates execution and cash drag, not changed retention-buffer selections.
- Rank weights 50/33.3/16.7, sector cap max two, $100 minimum normal adjustments. No 50% trigger and no earnings exit.
- Stop reference resets at each monthly rebalance open. Daily close <=75% (25% stop) or <=80% (20% stop) triggers full exit at next actual session open, regardless of $100 minimum. Hold cash until next monthly review, when the same stock may be selected again.
- All variants model portfolio floor at 85% of initial capital: daily-close breach sells all at next open and pauses without automatic restart. This is a close-to-next-open model, not an intraday reproduction of live monitoring.
- Full history uses synthetic dividend-adjusted OHLC and recorded adjusted fills; lab period uses raw bars, recorded fills and October-9 terminal closes independently verified in the October-11 monthly replay. Its ending NAV differs by $0.12 from saved lab due to closing-mark revisions. No fees, spreads, taxes, FX or cash interest.
- Archive uses current-universe selection: survivorship bias, incomplete historical fundamentals/coverage. This previously examined sample is not independent out-of-sample validation.
- Volatility and zero-risk-free Sharpe from daily sample returns with sqrt(252); initial capital prepended. Terminal positions marked, not liquidated.
- Validation: baseline recorded trades reproduced, all daily cash/NAV independently reconstructed, attribution reconciled, thresholds and next-session timing asserted, live labs unchanged.
