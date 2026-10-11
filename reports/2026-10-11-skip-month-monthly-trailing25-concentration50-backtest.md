# Skip-month conservative monthly 40/40/20: trailing 25% stop plus 50% concentration trigger

Period: **2022-02-07–2026-10-02**. Initial capital: **$3,000**. Backtest only; active labs unchanged.

## Result

The 50% trigger caused **three extra rebalances and eight extra trades**. Ending wealth was **$205.13 lower (−0.21%)** than trailing 25% alone. Sharpe improved marginally, volatility fell marginally, and maximum drawdown did not improve. The previously tested 60% trigger never fired and was identical to trailing-only.

| Metric | Trailing 25% only | Trailing 25% + 50% trigger |
|---|---:|---:|
| Ending value | $97,973.20 | $97,768.06 |
| Total return | 3,165.77% | 3,158.94% |
| CAGR | 111.67% | 111.58% |
| Sharpe | 1.939 | 1.946 |
| Annualized volatility | 43.58% | 43.36% |
| Maximum drawdown | −37.79% | −37.79% |
| Trades | 177 | 185 |
| Trailing-stop exits | 10 | 10 |
| Extra concentration rebalances | 0 | 3 |
| Maximum closing position weight | 55.21% | 52.23% |
| Closing sessions with a stock at least 50% | 19 | 3 |
| Closed-position win rate | 60.42% | 60.42% |
| Top-three positive-profit share | 71.07% | 71.32% |
| Months exceeding five trades | 3 | 6 |
| Orders above the five-per-month allowance | 3 | 7 |
| Average cash / equity | 2.24% | 2.36% |

The eight extra trades are not eight extra commissionable orders: the total above the five-per-month allowance rose by four. Fees are excluded from both results.

## When it triggered

| Signal close | Dominant stock | Closing weight | Next-session execution | Adjustment trades |
|---|---|---:|---|---:|
| 2024-11-08 | APP | 52.23% | 2024-11-11 | 3 |
| 2026-01-28 | WDC | 50.30% | 2026-01-29 | 3 |
| 2026-08-14 | SNDK | 50.17% | 2026-08-17 | 2 |

APP was trimmed and CVNA/NRG topped up. WDC was trimmed and WBD/GE topped up. In August 2026, the portfolio already had a stopped-out slot: SNDK and MRNA were both trimmed to their original rank shares, and the missing slot stayed cash. The rule does not force cash from a risk exit back into stocks mid-month.

## Exact rule

- Keep skip-month conservative monthly selection, sector cap two, 40/40/20 rank weights, buffer one, the initial-capital floor and trailing 25% stock stops.
- At each completed daily close, check stock value divided by portfolio equity **including cash**. A share **at least 50%** queues a next-actual-session-open rebalance.
- Use the last monthly ranking and reset surviving holdings toward those original rank shares, not equal weights or a new mid-month selection.
- Retain the **$100 minimum ordinary weight-adjustment trade**. Stop/floor exits take priority. A stopped-out slot stays cash until the scheduled monthly review; no mid-month re-entry.
- A scheduled monthly review absorbs a coincident concentration event; no double rebalance. Resizing preserves entry dates and trailing references.
- No earnings exit. No active lab settings or holdings were changed.

This is a daily-close trigger, **not a hard 50% cap**. The signal day's weight can exceed 50%, and intraday moves or overnight gaps can exceed it before execution.

## Interpretation

The rule reduced observed single-stock dominance without materially sacrificing historical return, but **did not improve the worst portfolio drawdown** or profit distribution. Only three historical activations support this comparison; a 0.007 Sharpe increase is not evidence of a reliably better strategy. It is best understood as a concentration preference, not proven extra downside protection. Trailing-only remains the simpler choice; a 50% trigger could be acceptable if limiting winner dominance is independently important to the investor.

## Validation and limits

- Original monthly-reference and trailing-only baselines reproduced trade-for-trade. Independent daily cash/NAV reconstruction and profit attribution reconciliation passed.
- Inclusive 50% and 60% boundaries, cash denominator, a funded rebalance with a stopped-out slot, no mid-month re-entry and retained entry dates passed synthetic checks. Actual concentration and stop executions were checked against the next cached exchange session.
- All lab files were byte-for-byte unchanged during the run.
- Identical frozen historical monthly baskets and cached adjusted OHLC/archived opening overrides as the earlier studies. Dynamic post-stop retention is not reconstructed; the reference universe/fundamental-coverage limitations remain.
- Sharpe uses daily arithmetic returns, sample standard deviation, 252-session annualization and zero risk-free rate. CAGR uses elapsed calendar time. Drawdown includes initial capital. Win rate counts closed holding episodes; concentration is the largest three ticker contributions divided by positive ticker P&L, including open positions.
- No fees, spreads, slippage, FX, taxes or cash interest. No out-of-sample validation. Multiple tested thresholds and a small activation sample limit confidence.

Assessment: **share with caveats**. Comparable historical results, no demonstrated material risk-adjusted improvement.

[Supporting JSON](data/2026-10-11-skip-month-monthly-trailing25-concentration50-backtest.json).

Reproduce: `python3 scripts/backtest_skip_month_monthly_earnings_exit.py --concentration50` with existing local research caches.
