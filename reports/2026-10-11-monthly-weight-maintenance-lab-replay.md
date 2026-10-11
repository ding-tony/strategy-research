# Three-position monthly: rank effectiveness and weight maintenance

Period: 2026-08-03–2026-10-09. Initial capital: $3,000. Research only; no lab changes.

| Variant | Ending value | Return | Annual volatility | Sharpe | Max drawdown | Orders |
|---|---:|---:|---:|---:|---:|---:|
| currentRankWeighted | $4,502.46 | 50.08% | 56.71% | 3.98 | -15.03% | 13 |
| equalWeightMaintenance | $4,288.25 | 42.94% | 46.00% | 4.23 | -11.79% | 13 |
| equalWeightRotationOnly | $4,318.19 | 43.94% | 46.43% | 4.28 | -11.79% | 11 |

3 identical review dates and baskets:
- 2026-08-03: WDC, SNDK, CNC
- 2026-09-08: MRNA, VLO, WBD
- 2026-10-05: MRNA, VLO, ON

## Caveats

- Frozen actual lab selection baskets and actual monthly dates; ranking not rerun.
- Raw closing marks and recorded lab fills used for both variants; no separate dividend credits, fees, spreads, FX or taxes.
- Equal initial allocations; rotation proceeds split equally among new entrants; continuing quantities unchanged. No 50% trigger or earnings exit.
- $100 minimum retained for matched configuration; all actual replay orders exceed it.
- Volatility and Sharpe use daily sample returns, sqrt(252) and zero risk-free rate; short sample is not a reliable forecast.
- Historic local price bars, particularly WBD, may contain stale or proxy observations; replay inherits lab data limits.

## Does the higher-ranked selection win more?

Completed scheduled review intervals only, next-review open-to-open total-return proxies. Rank is order among selected stocks, after sector and retention rules. Quarter-block resampling is descriptive, not an independent-sample significance test; adjacent blocks may remain dependent.

| Selected rank | Completed intervals | Average return | Median return | Positive return | Best in basket |
|---|---:|---:|---:|---:|---:|
| 1 | 2 | 11.43% | 11.43% | 50.0% | 50.0% |
| 2 | 2 | 29.52% | 29.52% | 100.0% | 50.0% |
| 3 | 2 | 8.31% | 8.31% | 100.0% | 0.0% |

Mean rank-one minus rank-three return: +3.12 percentage points; rank one beats rank three in 50.0% of completed intervals.
Average within-basket preference-return Spearman: 0.000.
Descriptive quarter-block 95% resampling range for mean rank-one minus rank-three: None; 1 quarter blocks. This is not proof of predictive skill.

### Entry-year checks

| Entry year | Completed intervals | Mean rank-one minus rank-three return |
|---|---:|---:|
| 2026 | 2 | +3.12 pp |

Recorded lab equity: $4,502.34; final-close replay difference: $+0.12.
Baseline reproduces every recorded trade. Equal-rotation checks verify unchanged continuing quantities, equal incoming allocations, zero cash and independent daily NAV reconciliation.
