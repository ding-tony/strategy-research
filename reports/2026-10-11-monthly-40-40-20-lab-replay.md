# October-2 aligned replay: monthly 40 40 20 lab replay

Period: 2026-08-03–2026-10-02. Starting capital: $3,000. Research only; no lab changes.

| Variant | Ending value | Return | Annual volatility | Sharpe | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|
| current | $4,090.42 | 36.35% | 56.64% | 3.423 | -15.03% | 9 |
| topPair | $4,174.57 | 39.15% | 54.62% | 3.744 | -14.11% | 9 |

## Winner breadth

| Variant | Closed-position win rate | Top-three positive-profit share | Stock-stop exits | Months >5 trades |
|---|---:|---:|---:|---:|---:|
| current | 66.67% | 92.63% | 0 | 1 |
| topPair | 66.67% | 91.35% | 0 | 1 |

## Method and validation

- Common cutoff 2026-10-02; saved October-9 replay curves and transactions truncated to the exact October-2 session. All returns, volatility, Sharpe, drawdown, CAGR, trade counts and profit attribution recomputed; no relabeling of October-9 metrics. Two monthly reviews and 44 daily observations.
- Raw cached daily closes and original recorded opening fills retained. Daily cash/quantities/NAV independently reconstructed and reconciled to every saved prefix observation; open-position P&L marked on October 2. No October-5 trades, October-9 terminal overrides or future exits included.
- Strategy settings are unchanged from the source study. Start date remains August 3, 2026, so these short lab replays must not be ranked directly against full-history tests.
- Current monthly lab replay 2026-08-03 through 2026-10-02, initial capital $3000.00, same two recorded monthly selections. Only weights change: 50/33.333/16.667 versus 40/40/20.
- Production monthly full weight maintenance, sector count cap two, $100 minimum ordinary adjustments, existing 25% daily-close-to-next-session-open stock stop, 85%-initial-capital close-to-next-open floor. No earnings exits or 50% concentration trigger.
- Stops do not rerank frozen selections. $100 minimum may leave small cash or weight deviations. No fees, spread, slippage, FX, taxes or cash interest.
- First allocations and all daily cash/NAV independently reconstructed; attribution reconciled and active lab files unchanged. No production configuration changes.
- Short-sample annualized statistics are not reliable forecasts. Original October-9 reports remain untouched. All active labs unchanged.

Supporting comparator metrics: [data/2026-10-11-monthly-40-40-20-lab-replay.json](data/2026-10-11-monthly-40-40-20-lab-replay.json). This public extract contains saved rules and metrics, not raw simulation ledgers.
Original reports are retained. Reproduce with `python3 scripts/align_strategy_comparator_cutoff.py`.
