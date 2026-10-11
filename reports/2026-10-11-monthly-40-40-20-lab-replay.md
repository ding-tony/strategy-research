# Monthly rank weights: 40/40/20 versus current

Period: 2026-08-03–2026-10-09. Initial capital: $3,000. Both include 25% stock stop. No lab changes.

| Weights | Ending value | Total return | Ann. volatility | Sharpe | Max drawdown | Orders |
|---|---:|---:|---:|---:|---:|---:|
| 50/33.3/16.7 | $4,502.46 | 50.08% | 56.71% | 3.975 | -15.03% | 13 |
| 40/40/20 | $4,525.30 | 50.84% | 53.69% | 4.217 | -14.11% | 13 |

40/40/20 ends $22.85 higher (+0.76 percentage points of return), with lower volatility and drawdown in this short replay. Both process three reviews and have no stop or capital-floor exit. This modest advantage does not override the mixed full-history comparison.

Recorded baskets: August 3 WDC/SNDK/CNC; September 8 MRNA/VLO/WBD; October 5 MRNA/VLO/ON. Raw fills and terminal marks are identical between weight variants.

## Calendar-year results

| Year | Current weights | 40/40/20 |
|---|---:|---:|
| 2026 (partial) | 50.08% | 50.84% |

## Concentration

| Weights | Maximum stock weight | Top-three positive-profit share | Stop exits |
|---|---:|---:|---:|
| current | 57.17% | 94.67% | 0 |
| topPair | 51.14% | 93.49% | 0 |

## Method and validation

- Current monthly lab replay 2026-08-03 through 2026-10-09, initial capital $3000.00, same three recorded monthly selections. Only weights change: 50/33.333/16.667 versus 40/40/20.
- Raw historical bars, recorded live-lab opening fills, and previously independently verified October-9 terminal closes. Baseline every trade and risk metrics reproduce the prior lab replay; terminal NAV differs from saved dashboard by $0.12 due to revised closes.
- Production monthly full weight maintenance, sector count cap two, $100 minimum ordinary adjustments, existing 25% daily-close-to-next-session-open stock stop, 85%-initial-capital close-to-next-open floor. No earnings exits or 50% concentration trigger.
- Stops do not rerank frozen selections. $100 minimum may leave small cash or weight deviations. No fees, spread, slippage, FX, taxes or cash interest.
- First allocations and all daily cash/NAV independently reconstructed; attribution reconciled and active lab files unchanged. No production configuration changes.
- Daily sample-return volatility/Sharpe annualized with sqrt(252), zero risk-free rate. Just three monthly reviews; annualized statistics and CAGR from this short sample are not reliable expectations.

Supporting results: [data/2026-10-11-monthly-40-40-20-lab-replay.json](data/2026-10-11-monthly-40-40-20-lab-replay.json).
