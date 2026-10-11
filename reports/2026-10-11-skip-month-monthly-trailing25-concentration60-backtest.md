# Monthly 40/40/20 with trailing 25% stop: 60% winner-dominance trigger

Period: **2022-02-07–2026-10-02**. Starting capital: **$3,000**. Research only; all active labs unchanged.

## Result

**The 60% trigger never fired.** The largest recorded closing position was **APP, 55.21%, on November 20, 2024**. Monthly weight maintenance already kept all positions below the tested threshold in this sample.

| Metric | Trailing 25% only | Trailing 25% + concentration 60% |
|---|---:|---:|
| Ending value | $97,973.20 | $97,973.20 |
| Total return | 3,165.77% | 3,165.77% |
| CAGR | 111.67% | 111.67% |
| Sharpe | 1.939 | 1.939 |
| Annualized volatility | 43.58% | 43.58% |
| Maximum drawdown | −37.79% | −37.79% |
| Trades | 177 | 177 |
| Trailing-stop exits | 10 | 10 |
| Extra concentration rebalances | 0 | 0 |
| Maximum closing position weight | 55.21% | 55.21% |
| Closed-position win rate | 60.42% | 60.42% |
| Top-three positive-profit share | 71.07% | 71.07% |

This threshold could be a rarely used safety exception, but these results provide **no evidence about its benefit or cost when triggered**. It is a concentration trigger, not a continuously enforced 60% cap; weights may exceed it before next-session execution.

For intuition, an initial 40% position needs approximately 125% growth relative to unchanged other holdings to become 60% of an otherwise fully invested portfolio. It needs only 50% relative growth to become 50%. Monthly resets substantially reduce the opportunity to reach 60%; skipped small adjustments can still leave weights away from targets.

## Exact tested rule

- Retain the trailing 25% stop and the existing monthly 40/40/20 strategy.
- At each completed daily close, calculate each position's share of total equity **including cash**.
- If any stock reaches or exceeds 60%, rebalance at the next actual session's open, using its **last monthly selection rank**, not a fresh mid-month ranking.
- Reset held stocks toward their original 40/40/20 target shares. Retain the $100 minimum ordinary weight-adjustment trade value.
- Stock-stop and capital-floor exits take priority. Do not buy a stopped-out ticker again mid-month; its target slot remains cash rather than redistributing its weight to survivors. Normal scheduled monthly reselection can re-enter it under the existing convention.
- If the next session is already a monthly review, that review absorbs the concentration event; do not execute two rebalances.
- An adjustment does not reset the trailing high or the position entry date.

No earnings exit, 50% trigger or $40 pilot threshold was added.

## Validation and limits

- Existing monthly-reference and trailing-only baselines reproduced trade-for-trade. The concentration variant's transactions and every daily equity/cash/weight record are identical to the trailing-only variant.
- Synthetic checks verify the inclusive 60% boundary, cash in the denominator, funded reset to 40%/40% with a stopped-out 20% slot left in cash, no stopped-stock re-entry, and retained entry dates. Because the historical trigger never fired, these synthetic checks are essential; the historical result does not exercise a triggered rebalance.
- Independent daily NAV and cash reconstruction, position-profit reconciliation, stock-stop next-session timing, and byte comparisons of all lab files passed.
- Same frozen reference monthly selections, cached adjusted OHLC and archived opening-fill overrides as the prior studies. Dynamic post-stop retention is not reconstructed. Current-universe survivorship and fundamental-coverage limits remain.
- No commissions, spread, slippage, FX, taxes or cash interest. In-sample evidence; no out-of-sample validation or guarantee of future concentration behaviour.
- Daily-close monitoring does not capture intraday concentration spikes or prevent overnight gaps. This rule has not been promoted to a lab.

Assessment: share with caveats. No observed effect in this sample; no claim that it improves risk-adjusted returns.

[Supporting data](data/2026-10-11-skip-month-monthly-trailing25-concentration60-backtest.json).

Reproduce: `python3 scripts/backtest_skip_month_monthly_earnings_exit.py --concentration60` with existing local research caches.
