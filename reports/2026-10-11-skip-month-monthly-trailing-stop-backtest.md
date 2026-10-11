# Skip-month conservative monthly 40/40/20: trailing 25% stop

Period: **2022-02-07–2026-10-02**. Initial capital: **$3,000**. Backtest only; no active lab, holding, order or production-rule changes.

## Finding

The trailing stop produces **4.98% more ending wealth** and a small Sharpe improvement, but **maximum drawdown worsens by 1.41 percentage points**. It is not a demonstrated risk-control upgrade. No statistical significance is established.

| Metric | Existing monthly-reference 25% stop | Trailing 25% stop |
|---|---:|---:|
| Ending value | $93,321.70 | $97,973.20 |
| Total return | 3,010.72% | 3,165.77% |
| CAGR | 109.47% | 111.67% |
| Sharpe | 1.915 | 1.939 |
| Annualized volatility | 43.63% | 43.58% |
| Maximum drawdown | −36.38% | −37.79% |
| Executed trades | 173 | 177 |
| Stock-stop exits | 4 | 10 |
| Closed-position win rate | 62.79% | 60.42% |
| Top-three positive-profit share | 71.60% | 71.07% |
| Average daily cash / equity | 0.55% | 2.24% |
| Months with more than five trades | 2 | 3 |
| Orders above five per month, summed | 2 | 3 |
| Capital-floor pauses | 0 | 0 |

## Exact rules

**Existing stop:** reset the stock reference to the monthly review opening price, even when a weight adjustment is skipped. A completed close at or below 75% of that reference triggers a full exit at the next session open.

**Trailing replacement:** seed the reference with the position's initial entry opening price, then raise it only when a completed daily close sets a higher high. Seeding protects an immediate entry-day decline before any closing high exists. The reference never moves down while the position remains open. Monthly reviews, partial sales and top-ups do not reset it. After a full exit, a new position receives a fresh entry reference. A completed close at or below 75% of the reference triggers the same full next-session-open exit.

Both variants leave proceeds in cash until the next monthly review. If that review coincides with the stop exit and selects the same ticker, the existing convention permits same-session re-entry. No cooldown was added.

Everything else stays unchanged: skip-month plus conservative investment factor, three positions, 40/40/20 monthly maintenance, sector count cap two, retention buffer one, $100 minimum ordinary weight adjustments, initial-capital 15% loss floor, no earnings exit and no 50% concentration trigger. The $40 pilot threshold was not tested here.

## Examples

- **DELL, June 4, 2024:** trailing reference was the May 29 close of approximately $173.19. June 3 closed at approximately $127.60, below 75% of that peak. The full position exited June 4 at approximately $127.76. The current monthly-reference variant did not have this exit.
- **APP, February 26, 2025:** trailing reference was the February 14 close of approximately $510.13. February 25 closed at approximately $377.06, triggering the exit. The next opening fill was approximately $328.47, **35.61% below the reference**, demonstrating that this is not a guaranteed 25% loss limit.
- **SNDK, July 6, 2026:** a July 2 closing breach of the June 25 peak triggered an exit at the July 6 open. That month's scheduled selection included SNDK, so it was bought again during the same review with a reset trailing reference. A second trailing exit followed July 17. This can create churn without permanently avoiding the declining stock.

All example prices use the same dividend-adjusted research series and archived fill overrides as the baseline, not an independent raw broker quote series.

Trailing exits can capture deteriorating winners earlier, but cash periods and subsequent re-entry alter the portfolio path. They do not necessarily lower aggregate drawdown. More stop exits with only four additional total trades also reflect changes in later monthly adjustments and rotations; stop count and trade-count difference are not interchangeable.

## Method and verification

- Baseline reproduced the saved skip40 strategy trade-for-trade, including prices and quantities; headline metrics agree within numerical tolerance.
- Use identical saved monthly selection baskets for both variants and production funded rebalance and next-open stock-exit execution. The research-only replacement changes only the stop reference. Frozen baskets isolate execution differences conditional on those selections; dynamic post-stop retention/reranking is not reconstructed.
- Daily references use only closes available through the signal session. Self-checks cover peak preservation across calendar months, no future-price leakage, an exact 25% breach, initial loss protection and reference reset on a fresh entry.
- Each trailing stop's reference and date are checked against its entry-to-signal price window; each exit is checked against the next actual benchmark session. Daily cash/NAV reconstructed independently, trade amounts checked, position profit reconciled, all live lab files verified unchanged.
- Sharpe uses daily arithmetic returns, zero risk-free rate and 252-session annualization. CAGR uses elapsed calendar time. No costs, slippage, FX, taxes or cash interest.
- Current cached universe, adjusted price and fundamental coverage limitations remain. In-sample comparison with repeated variant testing; this is not a forecast or proof of significance.
- This completed-close, next-session-open rule is not a broker intraday trailing-stop order. Execution gaps remain relevant; the [SEC's order guidance](https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-15) explains why stop triggers do not guarantee an execution price.

Assessment: share with caveats. Keep the existing lab unchanged unless a separate promotion decision is made.

Supporting comparator metrics: [data/2026-10-11-skip-month-monthly-trailing-stop-backtest.json](data/2026-10-11-skip-month-monthly-trailing-stop-backtest.json). This public extract contains saved rules and metrics, not raw simulation ledgers.

Reproduce: `python3 scripts/backtest_skip_month_monthly_earnings_exit.py --trailing-stop` using the existing local research caches.
