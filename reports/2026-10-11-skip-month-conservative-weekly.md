# Skip-month plus conservative factor: weekly rotation-only backtest

Period: 2022-02-07–2026-10-02. Initial capital $3,000. Research only; no lab changes.

## Conclusion

No clear weekly upgrade. Without a sector cap, adding conservative asset-growth ranking to skip-month reduces return from 3525.75% to 1466.74% and volatility from 56.13% to 38.88%; Sharpe improves from 1.662 to 1.723, still below matched normal + conservative at 1.803.

With a sector cap, skip-month + conservative returns 1568.48% versus 1520.53% for matched normal + conservative, but Sharpe falls from 1.832 to 1.802 and max drawdown deepens from -38.94% to -41.74%. The skip-conservative 50% trigger never fires, so it changes neither performance nor trades.

These are matched in-sample comparisons, not evidence of statistical significance or future superiority. The monthly result cannot be extrapolated to weekly execution.

| Strategy | Ending value | Return | CAGR | Volatility | Sharpe | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|---:|
| normalOriginal | $50,899.86 | 1596.66% | 83.86% | 38.39% | 1.785 | -45.99% | 239 |
| normalOriginalSector | $47,769.75 | 1492.33% | 81.37% | 36.67% | 1.813 | -38.94% | 235 |
| normalMatched | $51,802.99 | 1626.77% | 84.56% | 38.18% | 1.803 | -45.99% | 241 |
| normalMatchedSector | $48,616.00 | 1520.53% | 82.06% | 36.45% | 1.832 | -38.94% | 237 |
| pureSkipMatched | $108,772.47 | 3525.75% | 116.49% | 56.13% | 1.662 | -43.47% | 223 |
| pureSkipMatchedSector | $105,559.01 | 3418.63% | 115.10% | 56.02% | 1.652 | -46.80% | 221 |
| skipConservative | $47,002.35 | 1466.74% | 80.74% | 38.88% | 1.723 | -45.62% | 217 |
| skipConservativeSector | $50,054.35 | 1568.48% | 83.20% | 37.66% | 1.802 | -41.74% | 221 |
| normalOriginalSector50 | $48,018.73 | 1500.62% | 81.57% | 36.52% | 1.822 | -38.94% | 237 |
| skipConservativeSector50 | $50,054.35 | 1568.48% | 83.20% | 37.66% | 1.802 | -41.74% | 221 |

## Winner breadth and trading frequency

| Strategy | Closed-position win rate | Top-three positive-profit share | Distinct stocks | Months >5 trades | Earnings exits | 50% triggers |
|---|---:|---:|---:|---:|---:|---:|
| normalOriginal | 62.71% | 64.13% | 49 | 20 | 50 | 0 |
| normalOriginalSector | 62.07% | 63.38% | 48 | 21 | 50 | 0 |
| normalMatched | 62.18% | 64.65% | 50 | 20 | 50 | 0 |
| normalMatchedSector | 61.54% | 63.94% | 49 | 21 | 50 | 0 |
| pureSkipMatched | 64.55% | 61.67% | 38 | 16 | 57 | 0 |
| pureSkipMatchedSector | 66.06% | 58.11% | 39 | 14 | 56 | 0 |
| skipConservative | 63.55% | 63.62% | 47 | 17 | 49 | 0 |
| skipConservativeSector | 63.30% | 63.22% | 46 | 17 | 49 | 0 |
| normalOriginalSector50 | 62.07% | 63.31% | 48 | 21 | 50 | 1 |
| skipConservativeSector50 | 63.30% | 63.22% | 46 | 17 | 49 | 0 |

## Calendar-year returns (2022 and 2026 partial)

| Strategy | 2022 | 2023 | 2024 | 2025 | 2026 |
|---|---:|---:|---:|---:|---:|
| normalOriginal | 7.49% | 57.10% | 171.95% | 41.37% | 161.34% |
| normalOriginalSector | 3.64% | 46.47% | 172.00% | 41.66% | 172.22% |
| normalMatched | 7.49% | 57.10% | 171.95% | 41.37% | 165.98% |
| normalMatchedSector | 3.64% | 46.47% | 172.00% | 41.66% | 177.04% |
| pureSkipMatched | 26.36% | 40.37% | 247.36% | 108.21% | 182.64% |
| pureSkipMatchedSector | 36.19% | 39.78% | 247.39% | 108.21% | 155.54% |
| skipConservative | 11.18% | 25.92% | 163.65% | 63.19% | 160.11% |
| skipConservativeSector | 11.18% | 25.92% | 163.65% | 63.19% | 177.00% |
| normalOriginalSector50 | 4.18% | 46.47% | 172.00% | 41.66% | 172.22% |
| skipConservativeSector50 | 11.18% | 25.92% | 163.65% | 63.19% | 177.00% |

Normal versus skip conservative: different stocks at 118 of 243 reviews.

Normal versus skip conservativeSector: different stocks at 114 of 243 reviews.

History-eligibility exclusions at 24 reviews; details in JSON.

## Method and validation

- 2022-02-07 to 2026-10-02, $3,000, three equal-weight entry positions; weekly first available SPY session (holidays roll forward), rotation only, retention buffer one, earnings exits. No stock stop, capital floor, volatility overlay or leverage.
- Rotation sells full departing positions and divides available cash equally among new entrants; retained quantities stay unchanged. The $100 minimum affects only the optional 50% concentration-trigger weight adjustments, not rotation orders.
- Conservative means ascending negative annual asset-growth rank from SEC 10-K facts filed strictly before the prior-session signal date; added to ascending momentum rank. It is not a general quality or valuation filter.
- Normal matched, pure skip matched and skip-conservative share the same qualifying stocks. Begin with normal top-300 trailing-dollar-liquidity pool; symmetrically exclude stocks without skip-month history. Momentum ranks use the common liquid pool, consistent with the monthly study; conservative ranks retain the original top-300 calculation.
- Skip-month uses existing production formula: 252-session price return ending 21 sessions before signal. Existing prices rounded to two decimals before ranking; normal ranking uses 252-session return ending at signal.
- Max-two sector variants constrain stock count, not dollar exposure. Sector50 variants additionally restore equal weights when a held stock reaches 50% at prior close of weekly review; $100 ordinary adjustment minimum.
- Cached adjusted OHLC for fills and marks; SATS/ECHO stitched June 24, 2026. No archived-fill overrides in this fresh run. Raw market caches are unchanged. All eight ordinary variants rerank dynamically from their own holdings; not frozen target baskets.
- Historical earnings event archive used as in prior studies; missing/expired ticker coverage recorded. Actual point-in-time availability of scheduled earnings is not independently reconstructed.
- Current cached universe and sector labels, not complete historical membership; survivorship and incomplete fundamental coverage biases remain. Cached history shortages are not necessarily recent listings.
- No fees/spread/slippage/FX/tax or interest. Sharpe: sample daily arithmetic returns, zero risk-free rate, sqrt(252). Calendar years 2022 and 2026 are partial. Previously examined in-sample period, not new independent validation.
- Independent transaction-to-cash/NAV and position-episode attribution reconciled daily. Retained quantities, lagged signals, matching eligibility, sector count and nonnegative cash asserted. Live lab bytes unchanged.

Existing archive controls reproduce every target basket and trade count. Fresh cached-price ending-value differences versus archived fills: normalOriginal: $-22.2343; normalOriginalSector: $-20.6833; pureSkipMatched: $-0.0029. All are below 0.1% of ending value; differences are disclosed rather than forced to zero.

## Earnings archive gaps

- normalOriginal: ALL, BKR, CNC, EBAY, FANG, FICO, JBL, LHX, LVS, NRG, TPR, TRGP, TTWO, VRSN
- normalOriginalSector: ALL, APA, BKR, CNC, EBAY, FANG, FICO, JBL, LHX, LVS, NRG, TPR, TRGP, TTWO, VRSN
- normalMatched: ALL, BKR, CNC, EBAY, FANG, FICO, JBL, LHX, LVS, NRG, TPR, TRGP, TTWO, VRSN
- normalMatchedSector: ALL, APA, BKR, CNC, EBAY, FANG, FICO, JBL, LHX, LVS, NRG, TPR, TRGP, TTWO, VRSN
- pureSkipMatched: APA, BLDR, CF, EXE, FANG, MU, NRG, STLD, TRGP
- pureSkipMatchedSector: APA, BLDR, CF, FANG, NRG, STLD
- skipConservative: ALL, AMP, BKR, CHRW, CNC, EBAY, FANG, FICO, GEN, JBL, LUV, NRG, SPG, TPR, TTWO
- skipConservativeSector: ALL, AMP, BKR, CHRW, CNC, EBAY, FANG, FICO, GEN, JBL, LUV, NRG, SPG, TPR, TTWO
- normalOriginalSector50: ALL, APA, BKR, CNC, EBAY, FANG, FICO, JBL, LHX, LVS, NRG, TPR, TRGP, TTWO, VRSN
- skipConservativeSector50: ALL, AMP, BKR, CHRW, CNC, EBAY, FANG, FICO, GEN, JBL, LUV, NRG, SPG, TPR, TTWO

Supporting comparator metrics: [data/2026-10-11-skip-month-conservative-weekly.json](data/2026-10-11-skip-month-conservative-weekly.json). This public extract contains saved rules and metrics, not raw simulation ledgers.
