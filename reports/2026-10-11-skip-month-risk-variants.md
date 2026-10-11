# Skip-month weekly: maintenance, sector cap and volatility control

Period: 2022-02-07–2026-10-02; initial capital $3,000. Research only; live labs unchanged.

| Variant | Return | Volatility | Sharpe | Max drawdown | Orders | Months >5 orders |
|---|---:|---:|---:|---:|---:|---:|
| rotationOnly | 3525.75% | 56.13% | 1.662 | -43.47% | 223 | 16 |
| equalMaintenance | 3516.56% | 53.25% | 1.722 | -41.76% | 547 | 45 |
| sectorRotationOnly | 3118.26% | 55.49% | 1.628 | -46.94% | 225 | 16 |
| sectorMaintenance | 2689.13% | 50.18% | 1.683 | -39.79% | 551 | 47 |
| sectorMaintenanceVol40 | 1367.76% | 40.50% | 1.635 | -32.31% | 544 | 47 |

## Calendar-year checks (2022 and 2026 partial)

| Variant | 2022 | 2023 | 2024 | 2025 | 2026 |
|---|---:|---:|---:|---:|---:|
| rotationOnly | 26.36% | 40.37% | 247.36% | 108.21% | 182.64% |
| equalMaintenance | 28.22% | 32.39% | 234.64% | 117.38% | 192.89% |
| sectorRotationOnly | 36.19% | 39.78% | 247.39% | 108.21% | 133.73% |
| sectorMaintenance | 37.73% | 31.69% | 234.30% | 117.56% | 111.44% |
| sectorMaintenanceVol40 | 34.60% | 31.80% | 193.35% | 73.85% | 62.24% |

## Method and limits

- Current S&P 500 universe: survivorship bias; fundamentals use local filing history.
- Adjusted OHLC represents synthetic total returns; excludes fees, spreads, FX and taxes.
- Weekly variants exit before historical earnings; calendar coverage incomplete and dates may not have been known then. Monthly has no earnings exit.
- Capital floor disabled to measure continuous strategy outcomes. Current selection rules applied throughout, not a reconstruction of live lab versions.
- Terminal positions marked, not liquidated; excluded from closed-episode win rate. Ticker P&L includes terminal marks.
- Dollar profit concentration is affected by compounding and larger later positions.
- Ticker continuations join predecessor and successor price histories across symbol changes.
- Frozen archived target baskets and earnings exits; rankings not rerun. Sector cap means max two stocks per sector.
- All variants use $100 minimum maintenance trades. No 45% or 50% concentration trigger.
- Volatility control: 40% target, preceding 63 daily returns of unscaled sector-maintenance reference; weekly sizing, 25–100% exposure, no leverage. Full exposure during warmup.
- Cash earns zero interest. Fees excluded; excess orders assume five free orders per calendar month, not a euro fee estimate.
- Cached adjusted closing marks can have vendor revisions; exact baseline trade reproduction checked and terminal difference disclosed.
- Research comparison on already examined history, not an independent out-of-sample test.

Baseline terminal differences: {'rotationOnly': 0.0, 'sectorRotationOnly': 0.0}
Checks passed: exact archived baseline trades, independent daily cash/NAV and attribution, nonnegative cash, lagged-only volatility input, live lab bytes unchanged.
