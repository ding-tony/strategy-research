# Sector weekly: 50% position-trigger backtest

## Summary

Adding a weekly 50% concentration trigger had almost no impact in this history. It triggered once in 243 weekly decisions, added two orders, increased ending wealth by 0.52% relative to rotation only, and left maximum drawdown unchanged. One event does not establish a reliable improvement. Active labs were not changed.

## Rules and period

February 7, 2022–October 2, 2026; $3,000 initial capital; three positions; maximum two per sector; existing production ranking and buffer. Both versions use corrected funded rotation: unchanged positions remain untouched, and available replacement funds are split equally among incoming stocks.

The new rule checks the preceding trading close before each weekly rebalance. If any holding is at least 50% of equity including cash, the final selected basket is reset toward equal weights at the next rebalance open. Otherwise execution stays rotation-only. Historical earnings exits and the $100 minimum trade threshold remain active. This is not a continuous hard ceiling.

## Paired results

| Metric | Rotation only | 50% trigger |
|---|---:|---:|
| Ending value | $47,790.43 | $48,039.52 |
| Total return | 1,493.01% | 1,501.32% |
| Annualized return | 81.39% | 81.59% |
| Annualized volatility | 36.67% | 36.52% |
| Maximum drawdown | −38.94% | −38.94% |
| Sharpe, zero risk-free rate | 1.814 | 1.822 |
| Executed orders | 235 | 237 |
| Weekly decisions | 243 | 243 |
| Triggered resets | 0 | 1 |
| Top-three share of positive ticker P&L | 63.38% | 63.31% |

Stock selections were identical throughout. Daily closing equity was independently reconstructed from transactions and cached prices. Return, volatility, drawdown and P&L attribution reconcile; transaction cash and quantities remain nonnegative within floating-point tolerance. The trigger date was independently verified from pre-rebalance weights.

## Only one event, with an overlapping earnings exit

On May 9, 2022, OXY was 50.55% at the preceding close. The trigger added a partial OXY sale and a BKR top-up while MO rotated into ABBV. OXY then exited under the earnings rule the same day. This provides particularly weak evidence about protecting a long-held concentrated winner.

The full-history portfolio starts in 2022 rather than at the active labs’ inception. Its inherited quantities and weights therefore differ from the current labs. No recent MRNA trigger in this history does not contradict a concentrated MRNA position in the separate lab.

## Interpretation and limitations

There is no meaningful demonstrated risk improvement: volatility falls only 0.15 percentage points and the worst drawdown does not improve. A 50% threshold may still be a deliberate concentration guardrail, but this test cannot establish that the threshold is optimal. Keep it a candidate rather than treating the small return difference as proof.

Current-universe survivorship bias remains. Fundamentals use local filing history. Historical earnings coverage is incomplete, with possible hindsight in dates. Adjusted OHLC represents synthetic total returns; fees, spreads, FX and taxes are excluded. The capital floor is disabled, and terminal positions are marked rather than liquidated. Absolute historical returns are not reliable forecasts.

EchoStar prices were joined across the SATS-to-ECHO rename effective June 24, 2026, supported by the [company announcement](https://www.nasdaq.com/press-release/echostar-changing-stocker-ticker-sats-echo-marking-companys-next-era-earth-and-space). The successor provider series is already adjusted; its adjusted-close field uses that same closing-price basis.

## Reproduction and evidence

Run `scripts/backtest_profit_distribution.py` twice with `--end 2026-10-02 --ticker-continuations reports/data/2026-10-05-ticker-continuations.json`, once with `--skip-weight-adjustments` and once with `--weight-trigger-pct 50`. Then run `scripts/summarize_weight_trigger_backtest.py` for independent reconciliation.

- [Baseline replay](data/2026-10-05-sector-weekly-rotation-only-baseline.json)
- [50% trigger replay](data/2026-10-05-sector-weekly-50pct-trigger-backtest.json)
- [Validated comparison and event details](data/2026-10-05-sector-weekly-50pct-comparison.json)
- [Portable report input](data/2026-10-05-sector-weekly-50pct-artifact.json)

The Data Analytics portable HTML report was attempted but is blocked by the renderer’s horizontal-overflow check at a 1,440-pixel desktop viewport. No successful interactive report is claimed. The Markdown report and validated backtest evidence remain available.
