# Vinci SA — Sum-of-the-parts valuation

Part of the [European Power, Utilities & Infrastructure valuation portfolio](https://github.com/fcastillofadda/infrastructure-valuation).

**€127.24 per share versus €112.30 market (16 September 2026). Balance sheet 30 June 2026.**

## The question

Vinci's French motorways revert to the French state at no cost — Escota in 2032, Cofiroute in 2034,
ASF in 2036. They produced €4,784m of EBITDA in 2025, 37% of the group. A single perpetual DCF
capitalises that toll revenue for ever, which adds about €35bn of equity value (€62 per share) the
company will never collect. Vinci itself projects these cash flows only to contract end in its own
impairment tests (FY2025 financial statements, Note E).

## Method

| Block | Treatment |
|---|---|
| ASF, Cofiroute, Escota, Arcour/Arcos/A86 | Cash flows to contract expiry, terminal value = 0 |
| Gatwick + Edinburgh (freehold, 50.01%) | DCF to 2035 + Gordon terminal value; third-party 49.99% deducted on implied equity |
| OMA (29.99%), other airports | To concession end, terminal value = 0 |
| Other concessions (VINCI Highways) | To weighted concession end, terminal value = 0 |
| VINCI Energies, Cobra IS, VINCI Construction | 5-year DCF + Gordon terminal value with normalised capex |
| VINCI Immobilier | Book capital employed |

Bridge at 30 June 2026: net debt €22,450m, equity-accounted investments €2,051m, pensions net of tax,
minorities (Gatwick/Edinburgh and OMA on implied equity value, the rest at book). Lease repayments sit
inside free cash flow, so lease liabilities are not deducted twice. Diluted shares 561.9m.

## Results

| Block | € per share |
|---|---|
| French motorways | 47.1 |
| VINCI Energies | 33.9 |
| Gatwick + Edinburgh | 26.6 |
| Other airports | 26.4 |
| VINCI Construction | 16.6 |
| Other concessions | 7.4 |
| Cobra IS | 6.8 |
| OMA | 5.5 |
| Bridge items | (45.0) |
| **Implied value** | **127.2** |

Sensitivity: €107–158 per share across ±1pt on discount rates and ±0.5pt on terminal growth.

## Files

- `Vinci_SOTP_Model.xlsx` — Inputs, one sheet per block (cash flows to 2070), SOTP with per-share
  build, integrity checks and sensitivity, plus FY2023–25 historicals.

## Sources

Vinci 2025 Universal Registration Document, FY2025 consolidated financial statements (Notes C.1.2,
E, F.12, I.23.5, 29), half-year financial report 2026.

## Limitations

No network-level accounts exist for ASF, Escota and Cofiroute, so segment margins, capex and D&A are
applied pro rata to revenue. Airport margins are segment averages. "Other airports" and "other
concessions" use one weighted end date each. Equity-accounted stakes (Kansai, Budapest) are at book
value. Discount rates are judgement inputs, marked yellow in the workbook.
