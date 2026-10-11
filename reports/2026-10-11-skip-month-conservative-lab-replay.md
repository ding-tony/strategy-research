# October-2 aligned replay: skip month conservative lab replay

Period: 2026-08-03–2026-10-02. Starting capital: $3,000. Research only; no lab changes.

| Variant | Ending value | Return | Annual volatility | Sharpe | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|
| current | $4,090.42 | 36.35% | 56.64% | 3.423 | -15.03% | 9 |
| freshCurrent | $3,958.96 | 31.97% | 56.05% | 3.118 | -15.03% | 8 |
| skipConservative | $4,872.05 | 62.40% | 84.87% | 3.678 | -14.85% | 7 |

## Winner breadth

| Variant | Closed-position win rate | Top-three positive-profit share | Stock-stop exits | Months >5 trades |
|---|---:|---:|---:|---:|---:|
| current | 66.67% | 92.63% | 0 | 1 |
| freshCurrent | 100.00% | 97.00% | 0 | 0 |
| skipConservative | 100.00% | 100.00% | 0 | 0 |

## Method and validation

- Common cutoff 2026-10-02; saved October-9 replay curves and transactions truncated to the exact October-2 session. All returns, volatility, Sharpe, drawdown, CAGR, trade counts and profit attribution recomputed; no relabeling of October-9 metrics. Two monthly reviews and 44 daily observations.
- Raw cached daily closes and original recorded opening fills retained. Daily cash/quantities/NAV independently reconstructed and reconciled to every saved prefix observation; open-position P&L marked on October 2. No October-5 trades, October-9 terminal overrides or future exits included.
- Strategy settings are unchanged from the source study. Start date remains August 3, 2026, so these short lab replays must not be ranked directly against full-history tests.
- Both use monthly rank weights 50/33.333/16.667, sector count cap 2, retention buffer 1, $100 ordinary adjustment minimum, daily-close-confirmed 25% stock stop with next-session-open exit, fixed 85% initial-capital floor. No earnings exit or 50% concentration trigger.
- Current uses recorded live-lab baskets. FreshCurrent and skipConservative recompute normal versus skip-month momentum using identical cached histories, top-300 liquidity pool and SEC negative-asset-growth ranks. This third control separates signal changes from differences between recorded live selections and refreshed historical inputs. All pool stocks have skip-month history in this period; SEC filing dates strictly precede signal dates.
- Short-sample annualized statistics are not reliable forecasts. Original October-9 reports remain untouched. All active labs unchanged.

Supporting comparator metrics: [data/2026-10-11-skip-month-conservative-lab-replay.json](data/2026-10-11-skip-month-conservative-lab-replay.json). This public extract contains saved rules and metrics, not raw simulation ledgers.
Original reports are retained. Reproduce with `python3 scripts/align_strategy_comparator_cutoff.py`.
