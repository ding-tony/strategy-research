# Sector-cap weekly: 20% single-stock stop

Research only; no live lab changes.

## fullHistory: 2022-02-07–2026-10-02

| Variant | Total return | Annual volatility | Sharpe | Max drawdown | Orders | Stops |
|---|---:|---:|---:|---:|---:|---:|
| baseline | 1501.32% | 36.52% | 1.822 | -38.94% | 237 | 0 |
| stockStop20 | 1413.21% | 36.06% | 1.808 | -38.05% | 243 | 4 |

### Stop events

| Stock | Signal close | Exit open | Loss from weekly reference | Return after exit to next review |
|---|---|---|---:|---:|
| APP (stockStop20) | 2025-02-27 | 2025-02-28 | -24.00% | 11.90% |
| WDC (stockStop20) | 2026-06-26 | 2026-06-29 | -22.28% | 0.00% |
| SNDK (stockStop20) | 2026-07-16 | 2026-07-17 | -23.85% | 3.19% |
| SNDK (stockStop20) | 2026-07-28 | 2026-07-29 | -23.49% | 3.62% |

Portfolio-floor events: {"baseline": [], "stockStop20": []}

## Method and limitations

- Current S&P 500 universe: survivorship bias; fundamentals use local filing history.
- Adjusted OHLC represents synthetic total returns; excludes fees, spreads, FX and taxes.
- Weekly variants exit before historical earnings; calendar coverage incomplete and dates may not have been known then. Monthly has no earnings exit.
- Capital floor disabled to measure continuous strategy outcomes. Current selection rules applied throughout, not a reconstruction of live lab versions.
- Terminal positions marked, not liquidated; excluded from closed-episode win rate. Ticker P&L includes terminal marks.
- Dollar profit concentration is affected by compounding and larger later positions.
- Ticker continuations join predecessor and successor price histories across symbol changes.
- Frozen sector-weekly rank-ordered selection baskets and recorded earnings-exit dates; rankings/retention buffer not rerun after early exits.
- Three positions, equal entry allocation, max two per sector, rotation-only plus 50% prior-close concentration exception. $100 minimum ordinary adjustments, no minimum forced exits.
- 20% single-stock stop: reference resets at every scheduled weekly review open, including unchanged baskets; close <=80% of reference exits full position next actual session open. Cash held until next weekly review, when the same stock may be selected again.
- 50% exception remains checked weekly on the remaining portfolio after pending stop executions. Early exits can change concentration and rotation funding.
- No capital floor: sector-weekly archive and current sector lab have none configured. Earnings exits remain as archived. Cash has zero interest.
- Adjusted OHLC/synthetic total returns; recorded adjusted weekly open fills and earnings close fills reused; counterfactual stop exits use cached adjusted opens. Fees, spreads, FX and taxes excluded.
- Validation: baseline trades reproduce archived date, symbol, side, quantities, prices and gross values; independent daily NAV and attribution reconciliation; no negative cash; stop signals precede fills; live labs unchanged.
- Share with caveats: fixed-selection execution experiment, survivorship and earnings-calendar limitations inherited; not independent out-of-sample evidence.
