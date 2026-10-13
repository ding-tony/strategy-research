# Historical data recovery — partial, not yet decision-ready

Recovered 48 current-symbol series and 7 verified former-constituent histories. Confirmed 12 same-issuer ticker mappings against primary announcements/filings and local SEC identities. Original caches have recoverable backups; old reports and live labs were not replayed or changed.

Minimum skip-month history coverage improved from 82.38% to 87.33%. Review dates below 90% fell from 49 to 13, out of 81.

| Year | Before: lowest price coverage | After: lowest price coverage | Lowest price + investment-factor coverage |
|---|---:|---:|---:|
| 2020 | 85.15% | 87.33% | 86.73% |
| 2021 | 82.38% | 89.70% | 89.31% |
| 2022 | 83.17% | 91.68% | 91.49% |
| 2023 | 86.08% | 93.84% | 93.84% |
| 2024 | 87.87% | 95.03% | 94.83% |
| 2025 | 95.03% | 96.82% | 96.62% |
| 2026 | 97.61% | 98.61% | 98.21% |

## What remains

The historical-price API rejected a 2020 WBA request as not entitled under the available plan. Yahoo returned no series for many acquired/delisted names. Other responses are short fragments or potentially reused symbols; they remain quarantined, not substitutes for missing prices.

| Missing price series | Affected monthly reviews | Reason |
|---|---:|---|
| EA | 80 | missingPriorSessionBar |
| AVB | 79 | missingPriorSessionBar |
| HOLX | 76 | noCachedHistory |
| K | 72 | noCachedHistory |
| IPG | 71 | noCachedHistory |
| WBA | 68 | noCachedHistory |
| ANSS | 67 | noCachedHistory |
| HES | 67 | noCachedHistory |
| JNPR | 67 | noCachedHistory |
| DFS | 65 | noCachedHistory |
| QRVO | 60 | noCachedHistory |
| MRO | 59 | noCachedHistory |
| CTRA | 56 | noCachedHistory |
| WRK | 55 | noCachedHistory |
| CMA | 54 | noCachedHistory |
| PXD | 53 | noCachedHistory |
| CTLT | 51 | noCachedHistory |
| PEAK | 50 | noCachedHistory |
| SEE | 48 | noCachedHistory |
| ATVI | 46 | noCachedHistory |

## Fundamental coverage

SEC collection recovered 9 of 9 requested company-facts histories into a separate research database, including verified operating-company predecessors of XOM and BLK. The live database was not changed. Eligibility uses the existing investment-factor definition: two annual 10-K Assets observations filed strictly before the as-of date. Short listing history, missing facts, unsupported filing forms and identity changes are not silently filled.

## Interpretation

The original backtests remain exploratory. Better coverage is not complete coverage, and 90% is a diagnostic threshold, not certification. Missing names may materially change rankings. Do not publish a new preferred-strategy ranking until unresolved histories, identities, sectors and execution readers are reconciled on one frozen dataset.

Alias resolution is audited here only; research execution readers still require consistent identity handling.
Historical sector classifications and corporate-action total-return conventions are not independently validated.
Two as-filed annual Assets observations are required; absent scores are not imputed.
History availability is not strategy eligibility and does not certify every intervening daily session.
Membership source remains community-curated with limited primary-source spot checks.

## Verified ticker identities

- [BK → BNY, effective 2026-05-21](https://www.bny.com/corporate/global/en/about-us/newsroom/press-release/bny-announces-planned-change-of-stock-ticker-symbol-to-bny-130465.html)
- [MMC → MRSH, effective 2026-01-14](https://www.marsh.com/en/corp/about/news/marsh-mclennan-to-change-nyse-symbol-to-mrsh.html)
- [FB → META, effective 2022-06-09](https://investor.atmeta.com/investor-news/press-release-details/2022/Meta-Platforms-Inc.-to-Change-Ticker-Symbol-to-META-on-June-9/default.aspx)
- [ANTM → ELV, effective 2022-06-28](https://www.sec.gov/Archives/edgar/data/1156039/000115603922000081/elv-20220630.htm)
- [PKI → RVTY, effective 2023-05-16](https://www.sec.gov/Archives/edgar/data/31791/000003179124000004/pki-20231231.htm)
- [NLOK → GEN, effective 2022-11-08](https://investor.gendigital.com/news/news-details/2022/Introducing-Gen-The-Company-to-Power-Digital-Freedom/default.aspx/1000/)
- [FLT → CPAY, effective 2024-03-25](https://www.sec.gov/Archives/edgar/data/1175454/000162828024036429/cpay-20240630.htm)
- [ABC → COR, effective 2023-08-30](https://www.alliance-healthcare.com/sites/g/files/xpfdlm151/files/2023-08/8.%20%20Cencora%20Brand%20Launch%20Press%20Release%20-%20FINAL%208.18.23%20_0.pdf)
- [RE → EG, effective 2023-07-10](https://www.sec.gov/Archives/edgar/data/1095073/000109507324000009/eg-20231231.htm)
- [BLL → BALL, effective 2022-05-10](https://investors.ball.com/sec-filings/all-sec-filings/content/0000009389-22-000010/bll-20220427x8k.htm)
- [WLTW → WTW, effective 2022-01-10](https://www.sec.gov/Archives/edgar/data/1140536/000095017022001932/wtw-20211231.htm)
- [FI → FISV, effective 2025-11-11](https://www.sec.gov/Archives/edgar/data/798354/000079835426000009/fi-20251231.htm)
- [XOM predecessor CIK 34088 → successor 2115436, 2026-07-01](https://www.sec.gov/Archives/edgar/data/2115436/000119312526291990/d71068d8k12b.htm)
- [BLK predecessor CIK 1364742 → successor 2012383, 2024-10-01](https://www.sec.gov/Archives/edgar/data/1364742/000119312524229654/d856279d8k.htm)


This public copy contains the written findings. Raw data, caches and portfolio records are not published here.
