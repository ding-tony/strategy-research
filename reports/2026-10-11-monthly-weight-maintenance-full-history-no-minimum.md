# Three-position monthly: rank effectiveness and weight maintenance

Period: 2022-02-07–2026-10-02. Initial capital: $3,000. Research only; no lab changes.

| Variant | Ending value | Return | Annual volatility | Sharpe | Max drawdown | Orders |
|---|---:|---:|---:|---:|---:|---:|
| currentRankWeighted | $79,690.12 | 2556.34% | 43.69% | 1.84 | -38.82% | 170 |
| equalWeightMaintenance | $50,961.84 | 1598.73% | 39.00% | 1.76 | -34.38% | 164 |
| equalWeightRotationOnly | $51,073.30 | 1602.44% | 41.90% | 1.67 | -39.51% | 91 |
| rankWeightedNoMinimum | $79,065.90 | 2535.53% | 43.67% | 1.84 | -38.82% | 212 |

56 identical review dates and baskets:
- 2022-02-07: DVN, FANG, BX
- 2022-03-07: OXY, NOC, LHX
- 2022-04-04: OXY, BKR, ABBV
- 2022-05-02: OXY, BKR, MO
- 2022-06-06: OXY, BKR, MCK
- 2022-07-05: OXY, MCK, BKR
- 2022-08-01: OXY, MCK, BKR
- 2022-09-06: OXY, MCK, NOC
- 2022-10-03: OXY, MCK, NOC
- 2022-11-07: OXY, MCK, NOC
- 2022-12-05: OXY, FICO, BMY
- 2023-01-03: OXY, BKR, NOC
- 2023-02-06: OXY, ULTA, LVS
- 2023-03-06: GILD, ULTA, CI
- 2023-04-03: FICO, GILD, GE
- 2023-05-01: FICO, SBUX, GE
- 2023-06-05: UBER, FICO, NVDA
- 2023-07-03: UBER, NVDA, GE
- 2023-08-07: NVDA, UBER, GE
- 2023-09-05: NVDA, UBER, GE
- 2023-10-02: NVDA, UBER, GE
- 2023-11-06: NVDA, UBER, GE
- 2023-12-04: UBER, NVDA, GE
- 2024-01-02: UBER, NVDA, GE
- 2024-02-05: UBER, NVDA, GE
- 2024-03-04: CVNA, APP, GE
- 2024-04-01: CVNA, APP, DELL
- 2024-05-06: CVNA, APP, DELL
- 2024-06-03: CVNA, DELL, APP
- 2024-07-01: CVNA, APP, DELL
- 2024-08-05: CVNA, DELL, APP
- 2024-09-03: CVNA, APP, DELL
- 2024-10-07: CVNA, APP, NRG
- 2024-11-04: CVNA, APP, NRG
- 2024-12-02: CVNA, APP, NRG
- 2025-01-06: CVNA, APP, NRG
- 2025-02-03: CVNA, APP, NRG
- 2025-03-03: MMM, GE, NRG
- 2025-04-07: MMM, PM, MO
- 2025-05-05: TTWO, PM, MMM
- 2025-06-02: NRG, VRSN, MMM
- 2025-07-07: JBL, NRG, GE
- 2025-08-04: JBL, GE, NRG
- 2025-09-02: TPR, JBL, GE
- 2025-10-06: WDC, TPR, WBD
- 2025-11-03: WDC, WBD, GE
- 2025-12-01: WDC, WBD, GE
- 2026-01-05: WDC, WBD, GE
- 2026-02-02: WDC, WBD, ALB
- 2026-03-02: WDC, WBD, SNDK
- 2026-04-06: WDC, SNDK, WBD
- 2026-05-04: WDC, SNDK, WBD
- 2026-06-01: WDC, SNDK, WBD
- 2026-07-06: WDC, SNDK, WBD
- 2026-08-03: WDC, SNDK, CNC
- 2026-09-08: MRNA, VLO, WDC

## Caveats

- Current S&P 500 universe: survivorship bias; fundamentals use local filing history.
- Adjusted OHLC represents synthetic total returns; excludes fees, spreads, FX and taxes.
- Weekly variants exit before historical earnings; calendar coverage incomplete and dates may not have been known then. Monthly has no earnings exit.
- Capital floor disabled to measure continuous strategy outcomes. Current selection rules applied throughout, not a reconstruction of live lab versions.
- Terminal positions marked, not liquidated; excluded from closed-episode win rate. Ticker P&L includes terminal marks.
- Dollar profit concentration is affected by compounding and larger later positions.
- Ticker continuations join predecessor and successor price histories across symbol changes.
- Same frozen monthly targets and dates for both variants; recorded synthetic adjusted fills reused to isolate execution. Rankings not rerun.
- Equal initial allocations, retained quantities unchanged, incoming stocks split rotation proceeds equally. $100 minimum retained for both variants.
- Daily marks refreshed from local adjusted price cache; small vendor revisions may differ from original saved backtest terminal value.
- Zero-risk-free daily Sharpe, annualized using sqrt(252); no claim of statistical significance.
- rankWeightedNoMinimum alone removes the minimum trade amount; other variants retain $100. Frozen baskets preserve the source retention-buffer decisions. Capital floor remains disabled, so this is not an exact live-risk-control backtest.

## Does the higher-ranked selection win more?

Completed scheduled review intervals only, next-review open-to-open total-return proxies. Rank is order among selected stocks, after sector and retention rules. Quarter-block resampling is descriptive, not an independent-sample significance test; adjacent blocks may remain dependent.

| Selected rank | Completed intervals | Average return | Median return | Positive return | Best in basket |
|---|---:|---:|---:|---:|---:|
| 1 | 55 | 6.84% | 5.81% | 69.1% | 36.4% |
| 2 | 55 | 8.81% | 5.20% | 67.3% | 40.0% |
| 3 | 55 | 2.08% | 3.33% | 61.8% | 23.6% |

Mean rank-one minus rank-three return: +4.76 percentage points; rank one beats rank three in 60.0% of completed intervals.
Average within-basket preference-return Spearman: 0.136.
Descriptive quarter-block 95% resampling range for mean rank-one minus rank-three: [1.8188781716528732, 8.18824624971274]; 19 quarter blocks. This is not proof of predictive skill.

### Entry-year checks

| Entry year | Completed intervals | Mean rank-one minus rank-three return |
|---|---:|---:|
| 2022 | 11 | +5.70 pp |
| 2023 | 12 | +1.41 pp |
| 2024 | 12 | +4.75 pp |
| 2025 | 12 | +3.04 pp |
| 2026 | 8 | +11.05 pp |

Recorded lab equity: $79,690.12; final-close replay difference: $+0.00.
Baseline reproduces every recorded trade. Equal-rotation checks verify unchanged continuing quantities, equal incoming allocations, zero cash and independent daily NAV reconciliation.
