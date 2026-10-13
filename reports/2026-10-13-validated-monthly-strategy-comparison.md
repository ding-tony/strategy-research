# Corrected historical monthly comparison

2020-01-06–2026-10-02; initial $3,000. **Diagnostic only: historical constituent coverage remains incomplete.** Old reports are preserved; these results supersede neither live labs nor validated out-of-sample evidence.

| Strategy | Ending value | CAGR | Sharpe | Volatility | Max drawdown | Trades |
|---|---:|---:|---:|---:|---:|---:|
| Normal · 40/40/20 monthly | $66,459.88 | 58.37% | 1.514 | 34.35% | -32.59% | 308 |
| Skip-month · 40/40/20 monthly | $125,698.12 | 74.08% | 1.433 | 44.91% | -32.95% | 309 |
| Skip-month · equal monthly | $81,001.57 | 63.09% | 1.435 | 39.01% | -29.38% | 309 |
| Skip-month · equal rotation only | $79,339.03 | 62.59% | 1.446 | 38.52% | -34.08% | 153 |
| SPY buy-and-hold | $7,923.29 | 15.50% | 0.821 | 20.05% | -33.72% | 1 |

## Calendar-year returns

| Year | Normal 40/40/20 | Skip 40/40/20 | Skip equal monthly | Skip equal rotation | SPY |
|---|---:|---:|---:|---:|---:|
| 2020 | +9.93% | +9.06% | +4.05% | +4.68% | +18.84% |
| 2021 | +76.10% | +105.87% | +94.89% | +94.29% | +29.05% |
| 2022 | +16.10% | +30.90% | +28.71% | +31.55% | -18.18% |
| 2023 | +41.34% | +28.90% | +26.71% | +26.58% | +26.18% |
| 2024 | +74.61% | +86.50% | +70.74% | +69.08% | +24.89% |
| 2025 | +44.97% | +47.94% | +38.39% | +39.63% | +17.43% |
| 2026 YTD | +175.51% | +300.86% | +245.56% | +230.78% | +13.75% |

## Coverage and winner concentration

| Strategy | Lowest executed-review price eligibility | Reviews below 90% | Closed-position win rate | Largest winner profit share | Top-three profit share |
|---|---:|---:|---:|---:|---:|
| Normal · 40/40/20 monthly | 78.81% | 45 | 55.41% | 39.93% | 63.59% |
| Skip-month · 40/40/20 monthly | 78.81% | 45 | 57.33% | 43.33% | 72.94% |
| Skip-month · equal monthly | 78.81% | 45 | 56.00% | 36.85% | 67.81% |
| Skip-month · equal rotation only | 78.81% | 45 | 56.00% | 37.12% | 67.47% |

Coverage above includes strategy price/liquidity eligibility after strict history and sector availability checks; it is not the earlier raw-history availability metric. Counts cover executed reviews only, excluding paused reviews. Below-gate trading is diagnostic and not live-equivalent.

## Fixes and limits

- All variants use the same fingerprinted, frozen recovered dataset and dated historical membership; verified same-issuer renames use one canonical security identity.
- Signals use the prior SPY session only. Both momentum variants require the same complete 274-session close/volume window; missing, stale, invalid or unknown-sector names are explicitly excluded, not imputed.
- Normal and skip-month conservative momentum share top-300 liquidity and as-filed annual negative asset-growth ranking; normal includes the latest month and skip-month excludes 21 sessions.
- Three stocks, max two per sector, buffer one, monthly first Monday or next SPY session, 25% entry-seeded highest-close trailing stop with next-open exit; stopped cash waits for the monthly review.
- The 15% initial/risk-cycle capital floor liquidates next open and re-enters only at a later monthly review after five completed SPY closes above their own MA200. This is not a 15% peak-to-trough drawdown guarantee.
- Normal and skip-month reset to 40/40/20; equalMonthly resets to thirds; equalRotationOnly keeps survivor quantities and allocates replacement cash equally. No minimum adjustment or earnings exit.
- All reported comparisons are gross of fees, spread, slippage, tax and FX; no cash interest. Sharpe uses daily arithmetic returns, sample standard deviation, sqrt(252), zero risk-free rate; CAGR is separately reported.
- Adjusted OHLC approximates dividend-reinvested exposure; split/dividend/spin-off accounting and historical sector classifications remain unverified. Current frozen sectors are proxies, not point-in-time labels.
- This reruns an already optimized in-sample history. It is not out-of-sample validation, and missing constituents can change rankings. Live lab rules and records are unchanged.

Frozen input identifier: `2026-10-13-validated-backtest-inputs`; manifest fingerprint: `c9c82edcea39537c9131baed7ab8a0b871dcf850ccb5fa0ad12094d6072b4a24`.

- Historical sector labels unavailable: frozen current-sector proxy.
- Vendor adjusted OHLC is a total-return proxy, not independently verified corporate-action accounting.
- Delisted histories remain incomplete. Benchmark sessions come from frozen SPY, not an independent exchange calendar.


This public copy contains the written findings. Raw data, caches and portfolio records are not published here.
