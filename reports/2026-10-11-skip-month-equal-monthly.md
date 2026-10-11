# Skip-month monthly: equal weights versus rank weights

Period: 2022-02-07–2026-10-02. Initial capital: $3,000. Three stocks, sector cap two, monthly weight maintenance, $100 ordinary minimum. Research only.

| Weight rule | Stock stop | Ending value | Total return | CAGR | Ann. volatility | Sharpe | Max drawdown | Orders |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| Rank | None | $90,858.95 | 2928.63% | 108.27% | 57.69% | 1.564 | -51.18% | 168 |
| Rank | 25% | $99,045.66 | 3201.52% | 112.17% | 55.33% | 1.639 | -46.01% | 180 |
| Equal | None | $69,969.10 | 2232.30% | 96.89% | 53.48% | 1.538 | -49.37% | 152 |
| Equal | 25% | $77,117.60 | 2470.59% | 101.05% | 51.36% | 1.619 | -45.11% | 164 |

Current conservative monthly with 25% stop reference: return 2729.37%, volatility 42.81%, Sharpe 1.899, maximum drawdown -35.84%, 174 orders.

Equal weights reduce volatility and orders, but give up more return than the risk reduction compensates for in daily Sharpe terms. With the 25% stop, equal weights end with 22.14% less wealth than rank weights; volatility falls 3.97 percentage points and maximum drawdown improves only 0.90 points. Equal-weight skip-month also trails the current conservative monthly reference in return and risk metrics. These are descriptive results, not evidence of future superiority.

## Winner breadth

| Variant | Closed-position win rate | Closed episodes | Largest winner share | Top-three positive profit share | Stop exits |
|---|---:|---:|---:|---:|---:|
| rank | 53.12% | 32 | 31.21% | 68.96% | 0 |
| rankStop25 | 53.66% | 41 | 30.49% | 69.70% | 11 |
| equal | 53.12% | 32 | 25.64% | 66.40% | 0 |
| equalStop25 | 56.10% | 41 | 25.42% | 66.78% | 11 |

## Method and validation

- Same 2022-02-07 to 2026-10-02 archive period, $3000, 3 stocks, rank targets 50/33.3/16.7 versus equal targets 33.3/33.3/33.3, sector count cap 2, retention buffer 1, $100 minimum ordinary adjustments, monthly weight maintenance. No earnings exit or 50% concentration trigger.
- Current conservative ranking uses archived monthly baskets (momentum plus conservative investment factor). Skip-month uses price momentum only, the existing lab scoring formula and top 300 trailing-dollar-liquidity pool, prior-session data only, monthly selection with the production retention/sector selector. This compares ranking families, not a one-factor skip-only change.
- Monthly dates are the archived first weekly review session in each month, not always the exact first trading day. Sector cap limits stock count, not sector dollar weight.
- Paired stop comparisons freeze each no-stop target schedule, matching the earlier monthly stop study. This isolates execution; it does not rerank retention after stop exits.
- Existing skip-month formula is a 252-session return ending 21 sessions before the signal, not a newly defined canonical academic 12-1 signal.
- 25% close-confirmed stop uses production implementation; next-session-open full exit, cash until monthly review. Fixed 85% starting-capital floor is daily-close-to-next-open; no interest.
- Synthetic dividend-adjusted prices and previously recorded monthly fills, no fees/spread/slippage/FX/tax. Current cached universe, not complete dated membership: survivorship and incomplete fundamental-availability biases. Previously examined in-sample period, not independent validation.
- Sharpe uses sample daily arithmetic returns, zero risk-free rate, sqrt(252). Independently reconciled cash/NAV and episode P&L; prior baseline and stop study reproduced. All active labs unchanged.
- New equal-weight variants target 1/3 per stock at every monthly review, including unchanged stocks, subject to $100 ordinary-adjustment minimum. NOT rotation only. No 50% concentration trigger.
- All four variants replay the identical archived skip-month rank-ordered basket schedule. Weight is the only intended change within each stop/no-stop pair; targets are not reranked following stop exits.
- Rank variants reproduced prior result and every recorded fill. Equal initial buys asserted at $1000 each; independent daily cash/NAV and episode profit checks passed. Active labs unchanged.

Supporting results: [data/2026-10-11-skip-month-equal-monthly.json](data/2026-10-11-skip-month-equal-monthly.json).
