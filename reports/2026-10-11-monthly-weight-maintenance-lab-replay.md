# October-2 aligned replay: monthly weight maintenance lab replay

Period: 2026-08-03–2026-10-02. Starting capital: $3,000. Research only; no lab changes.

| Variant | Ending value | Return | Annual volatility | Sharpe | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|
| currentRankWeighted | $4,090.42 | 36.35% | 56.64% | 3.423 | -15.03% | 9 |
| equalWeightMaintenance | $4,061.42 | 35.38% | 46.96% | 3.937 | -11.79% | 9 |
| equalWeightRotationOnly | $4,061.42 | 35.38% | 46.96% | 3.937 | -11.79% | 9 |

## Winner breadth

| Variant | Closed-position win rate | Top-three positive-profit share | Stock-stop exits | Months >5 trades |
|---|---:|---:|---:|---:|---:|
| currentRankWeighted | 66.67% | 92.63% | 0 | 1 |
| equalWeightMaintenance | 66.67% | 86.62% | 0 | 1 |
| equalWeightRotationOnly | 66.67% | 86.62% | 0 | 1 |

## Method and validation

- Common cutoff 2026-10-02; saved October-9 replay curves and transactions truncated to the exact October-2 session. All returns, volatility, Sharpe, drawdown, CAGR, trade counts and profit attribution recomputed; no relabeling of October-9 metrics. Two monthly reviews and 44 daily observations.
- Raw cached daily closes and original recorded opening fills retained. Daily cash/quantities/NAV independently reconstructed and reconciled to every saved prefix observation; open-position P&L marked on October 2. No October-5 trades, October-9 terminal overrides or future exits included.
- Strategy settings are unchanged from the source study. Start date remains August 3, 2026, so these short lab replays must not be ranked directly against full-history tests.
- Frozen actual lab selection baskets and actual monthly dates; ranking not rerun.
- Raw closing marks and recorded lab fills used for both variants; no separate dividend credits, fees, spreads, FX or taxes.
- Equal initial allocations; rotation proceeds split equally among new entrants; continuing quantities unchanged. No 50% trigger or earnings exit.
- $100 minimum retained for matched configuration; all actual replay orders exceed it.
- Volatility and Sharpe use daily sample returns, sqrt(252) and zero risk-free rate; short sample is not a reliable forecast.
- Historic local price bars, particularly WBD, may contain stale or proxy observations; replay inherits lab data limits.
- Short-sample annualized statistics are not reliable forecasts. Original October-9 reports remain untouched. All active labs unchanged.

Supporting comparator metrics: [data/2026-10-11-monthly-weight-maintenance-lab-replay.json](data/2026-10-11-monthly-weight-maintenance-lab-replay.json). This public extract contains saved rules and metrics, not raw simulation ledgers.
Original reports are retained. Reproduce with `python3 scripts/align_strategy_comparator_cutoff.py`.
