# Historical index membership and backtest readiness

## Executive Summary

The membership timeline now extends through 2026-10-12 and reconciles exactly to the current anchor: 503 share classes. Verified September and October changes have been added using their effective dates. Earlier historical records are preserved.

Backtests are still not ready for firm strategy rankings: minimum skip-month history availability is 82.38%, and 49 of 81 monthly review dates fall below 90%. Membership and price completeness are separate tests.

## Recent membership gaps are repaired

| Effective date | Added | Removed |
|---|---|---|
| 2026-09-21 | BE, P, ILMN | TAP, TTD, BLDR |
| 2026-10-01 | VYLR | None |
| 2026-10-06 | TWLO, SKYD | WBD, CTVA, PSKY |

The September 21 change was missing from the old file despite occurring before the October 2 backtest cutoff. Vylor is temporarily added October 1 while Corteva remains until October 6, as the official index table specifies. PSKY → SKYD is a ticker change, not an extra company.

The canonical manifest fingerprints the generated CSV. Future research readers reject dates beyond its verified endpoint and reject an altered dataset until its manifest is rebuilt. The previous September 8 file remains preserved.

## Historical prices remain the limiting evidence

Coverage here means a historical member has the exact previous-session bar and at least 274 valid close-and-volume observations for skip-month momentum. This measure does not substitute for the strategy’s complete price, liquidity and fundamental eligibility checks.

| Year | Monthly review dates | Lowest skip-history coverage | Reviews below 90% |
|---|---:|---:|---:|
| 2020 | 12 | 85.15% | 12 |
| 2021 | 12 | 82.38% | 12 |
| 2022 | 12 | 83.17% | 12 |
| 2023 | 12 | 86.08% | 12 |
| 2024 | 12 | 87.87% | 1 |
| 2025 | 12 | 95.03% | 0 |
| 2026 | 9 | 97.61% | 0 |

Missing series include removed companies and renamed symbols. A recent IPO can legitimately lack the required lookback; an older company whose prices are missing cannot be treated the same way without checking its listing history. The supporting JSON lists every affected ticker at every review.

## What must happen before strategy rankings are reused

1. Obtain or correctly map the missing historical prices, especially removed/delisted constituents. Verify security identity and corporate actions before linking old and new symbols; never substitute an unrelated successor’s returns.
2. Extend the same audit to historical fundamentals and sector classifications. Current sector labels and incomplete filing coverage are separate remaining biases.
3. Rerun the candidate strategies using one frozen dataset version and the same selection, date and execution conventions. Preserve old reports as diagnostic results rather than overwrite them.

## Sources and limits

The pre-existing file matches the downloaded upstream source through August 18 exactly; its September 8 row only repeated that final snapshot. Structural checks and ten dated membership spot checks passed. The current snapshot is a separate reconciliation anchor, not independent certification of all historical membership changes.

Historical data come from a community-maintained compilation; its author explicitly describes selected-change and delisted-price limitations. Membership counts near 500 and a matching endpoint do not prove all intervening events are complete.

[Historical source](https://github.com/fja05680/sp500). [Current anchor](https://github.com/chinobing/historical_sp500_constituents).

- [Verified event effective 2026-09-21](https://press.spglobal.com/2026-09-04-Bloom-Energy%2C-Illumina%2C-and-Everpure-Set-to-Join-S-P-500-Others-to-Join-S-P-100%2C-S-P-MidCap-400%2C-and-S-P-SmallCap-600)
- [Verified event effective 2026-10-01](https://press.spglobal.com/2026-10-01-Vylor-Added-to-the-S-P-500-Twilio-Set-to-Join-S-P-500-Others-to-Join-S-P-MidCap-400-and-S-P-SmallCap-600)
- [Verified event effective 2026-10-06](https://press.spglobal.com/2026-10-01-Vylor-Added-to-the-S-P-500-Twilio-Set-to-Join-S-P-500-Others-to-Join-S-P-MidCap-400-and-S-P-SmallCap-600)


This public copy contains the written findings. Raw data, caches and portfolio records are not published here.
