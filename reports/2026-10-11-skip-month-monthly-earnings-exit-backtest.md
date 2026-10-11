# Skip-month conservative monthly 40/40/20: pre-earnings exits

Period: **2022-02-07–2026-10-02**. Initial capital: **$3,000**. Backtest only; active labs and their rules are unchanged.

## Rule tested

Sell the whole position at the last actual market-session close before its historical earnings date. Keep the proceeds in cash until the next scheduled monthly review. This is an unconditional earnings exit, not a stop triggered by a bad earnings reaction. There is no immediate replacement or additional entry exclusion.

Keep all other reference settings: skip-month momentum plus conservative investment factor; three positions; 40/40/20 monthly target weights; sector count cap two; retention buffer one; $100 minimum ordinary weight adjustments; 25% monthly-reference close-to-next-open stock stop; 15% loss floor against initial capital; no 50% concentration trigger. No $40 pilot threshold was introduced.

## Actual strategy comparison, including the capital floor

| Metric | Current strategy | Add pre-earnings exits |
|---|---:|---:|
| Ending value | $93,321.70 | $2,581.77 |
| Total return | 3,010.72% | −13.94% |
| Executed trades | 173 | 25 |
| Earnings exits | 0 | 4 |
| Capital-floor pause | None | June 24, 2022 |

The earnings-exit variant closed June 23, 2022 at $2,543.19, below the $2,550 floor. It liquidated at the next session open and stayed paused through the cutoff. Its subsequent cash-only period is **not evidence of low ongoing strategy risk**. Its full-period volatility of 9.07% and Sharpe of −0.311 are therefore not useful comparisons of continuously active strategies.

Early earnings exits included DVN on February 14 ahead of February 15, FANG on February 18 ahead of February 22, NOC on April 27 ahead of April 28, and OXY on May 9 ahead of May 10. FANG's exit accounts for the February 21 market holiday.

## Continuous-run diagnostic: capital floor disabled on both sides

This separate comparison removes only the capital floor to examine the longer-run earnings-exit effect. It is **not the current strategy or a proposed lab replacement**. The baseline is unchanged because it never breached that floor.

| Metric | No earnings exits | Pre-earnings exits |
|---|---:|---:|
| Ending value | $93,321.70 | $37,517.09 |
| Total return | 3,010.72% | 1,150.57% |
| CAGR | 109.47% | 72.18% |
| Sharpe | 1.915 | 1.620 |
| Annualized volatility | 43.63% | 38.00% |
| Maximum drawdown | −36.38% | −32.17% |
| Executed trades | 173 | 210 |
| Earnings exits | 0 | 56 |
| Closed-position win rate | 62.79% | 67.47% |
| Top-three positive-profit share | 71.60% | 72.96% |
| Average daily cash / equity | 0.55% | 18.20% |
| Months with more than five trades | 2 | 7 |
| Orders above five per month, summed | 2 | 10 |

Lower volatility and a 4.21-percentage-point drawdown improvement accompany about **59.80% less ending wealth**, a lower Sharpe, more trading and substantial time in cash. Higher win rate does not compensate for smaller aggregate gains. Profit concentration does not improve. These results do not establish that earnings exits are universally bad, but do not support adding this unconditional rule to this strategy.

## Method, coverage and validation

- Same dates, starting capital, adjusted price series, archived opening-fill overrides and monthly baskets as the saved skip40 reference. Baseline reproduced trade-for-trade and metric-for-metric.
- Reuse production funded rebalance, daily stock-stop and full-position earnings-exit execution. For earnings timing only, use cached SPY sessions instead of the production weekday approximation, covering holidays and weekend announcements. Self-checks cover a holiday and a weekend report.
- Reuse the reference frozen monthly selections on both sides. Post-exit retention is not dynamically reranked; this isolates the exit/cash effect conditional on those baskets, rather than simulating every downstream selection change in production.
- Merge actual reported dates from the local earnings cache with the legacy earnings-event archive. Duplicate ticker/date records are removed. All held sessions have surrounding report dates, with no bracket gap exceeding 150 days; this check does not prove every historical announcement is correct or complete. No diagnostic purchase occurred on its ticker's recorded earnings date.
- Historical report dates are proxies for dates that would have been known beforehand. Announcement times, revisions and reschedules are not reconstructed. Conservatively exit before the report date even for an after-close announcement.
- Primary-source spot checks confirmed [Moderna's July 31, 2026 release](https://investors.modernatx.com/quarterly-results), [Baker Hughes' Sunday July 26, 2026 release](https://investors.bakerhughes.com/news/press-releases/news-details/2026/Baker-Hughes-Announces-Second-Quarter-2026-Results/default.aspx), and [Dell's September 1, 2026 release](https://investors.delltechnologies.com/news-events/press-releases). These checks do not validate the entire historical calendar.
- Independent daily cash and NAV reconstruction, trade amount checks, position profit reconciliation and live-state byte comparisons passed. No lab state or production setting was changed.
- Cached current-universe survivorship and fundamental-coverage limitations remain. No commissions, spreads, slippage, FX, taxes or cash interest. In-sample evidence, not a forecast or proof of significance.

Supporting comparator metrics: [data/2026-10-11-skip-month-monthly-earnings-exit-backtest.json](data/2026-10-11-skip-month-monthly-earnings-exit-backtest.json). This public extract contains saved rules and metrics, not raw simulation ledgers.

Reproduce: `python3 scripts/backtest_skip_month_monthly_earnings_exit.py` with the existing local research caches.
