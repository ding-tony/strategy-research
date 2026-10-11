# Monthly rotation-only position count: October-2 aligned backtest

Period: 2022-02-07–2026-10-02. Starting capital: $3,000. Research only; no lab changes.

| Variant | Ending value | Return | Annual volatility | Sharpe | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|
| 3 | $19,250.57 | 541.69% | 37.34% | 1.262 | -40.43% | 97 |
| 4 | $17,452.88 | 481.76% | 33.78% | 1.295 | -35.46% | 142 |
| 5 | $14,614.47 | 387.15% | 30.40% | 1.276 | -33.13% | 187 |

## Winner breadth

| Variant | Closed-position win rate | Top-three positive-profit share | Stock-stop exits | Months >5 trades |
|---|---:|---:|---:|---:|---:|
| 3 | 61.70% | 59.63% | 0 | 1 |
| 4 | 60.87% | 55.20% | 0 | 6 |
| 5 | 52.75% | 54.78% | 0 | 10 |

## Method and validation

- Same 3/4/5-position conservative momentum strategy, dated-membership selector, monthly first weekly review, top-300 liquidity, sector cap two, retention buffer one, equal entry weights and rotation only. No earnings exits, minimum order, stock stop, capital floor or concentration trigger.
- Rerun through October 2 using adjusted cached OHLC. The final scheduled monthly review is September 8 and the next is October 5: the extension adds 18 daily valuations, not extra trades or membership decisions. September-8 membership snapshot covers every selection date; no post-snapshot membership assumptions are needed.
- Original September-8 order counts reproduced and every three-position basket matched the original archived replay. Refreshed-cache terminal values and Sharpe agree within 0.5% and 0.005 respectively; exact differences recorded in supporting JSON, not attributed to the cutoff extension. Continued positions remain untouched; rotations fully funded with zero residual cash. Independent daily NAV and episode attribution reconciled.
- Historical membership filters cached current-universe stocks; missing former constituents, current sector labels and incomplete local filing history leave survivorship and availability biases. No fees, spreads, slippage, FX or tax. Dated-membership results are not apples-to-apples with current-universe studies even though the cutoff matches.
- Original September report remains unchanged. All active labs unchanged. Sharpe uses sample daily arithmetic returns, sqrt(252), zero risk-free rate. Previously examined in-sample period, not independent validation.

Supporting comparator metrics: [data/2026-09-29-monthly-rotation-position-count-backtest.json](data/2026-09-29-monthly-rotation-position-count-backtest.json). This public extract contains saved rules and metrics, not raw simulation ledgers.
Original reports are retained. Reproduce with `python3 scripts/align_strategy_comparator_cutoff.py`.
