# Monthly rotation-only position-count comparison

Period: **7 February 2022–8 September 2026**. Initial capital: **$3,000**.

This isolates position count while holding the other rules constant: production conservative-momentum ranking, dated S&P membership, top 300 by trailing dollar liquidity, maximum two positions per sector, retain-through-one-extra-rank buffer, monthly review, rotation-only execution, no minimum-order filter, and no earnings exit.

## Results

| Positions | Ending value | Total return | CAGR | Ann. volatility | Sharpe | Max drawdown | Orders |
|---:|---:|---:|---:|---:|---:|---:|---:|
| 3 | **$18,066** | **502.2%** | **48.0%** | 37.5% | 1.24 | -40.4% | **97** |
| 4 | $16,775 | 459.2% | 45.6% | 33.9% | **1.28** | -35.5% | 142 |
| 5 | $13,964 | 365.5% | 39.9% | **30.4%** | 1.26 | **-33.1%** | 187 |

## Marginal trade-off

- Moving from three to four positions costs 2.37 percentage points of CAGR, while reducing volatility by 3.60 points and improving maximum drawdown by 4.97 points.
- Moving from four to five costs another 5.71 points of CAGR, while reducing volatility by 3.42 points and improving drawdown by only 2.33 points.
- Four positions has the highest Sharpe. The fifth position adds less downside protection while diluting the stronger-ranked holdings more heavily.

## Execution

| Positions | Orders | Months above five orders | Orders above five-trade allowance |
|---:|---:|---:|---:|
| 3 | 97 | 1 | 1 |
| 4 | 142 | 6 | 8 |
| 5 | 187 | 10 | 20 |

At a €1,200 starting balance, the initial allocations would be €400, €300, and €240 per position respectively. Rotation-only avoids weight-maintenance trades, so no minimum-order rule is needed.

## Conclusion

**Four positions is the best balance in this sample.** It retains most of the three-position return, materially reduces volatility and drawdown, and has the highest risk-adjusted return. Five positions is preferable only if minimizing volatility matters more than the additional loss of return and higher transaction count.

The replay still has survivorship bias from missing former constituents, uses current rules retrospectively and locally available filing history, and excludes fees, spreads, slippage, FX, and taxes.

Structured results: [data/2026-09-29-monthly-rotation-position-count-backtest.json](data/2026-09-29-monthly-rotation-position-count-backtest.json).
