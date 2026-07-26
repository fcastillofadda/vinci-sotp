# Vinci SA — DCF Valuation

**Euronext Paris: DG** · Construction + concessions (motorways, airports) · Valuation date 4 Jul 2026

A discounted cash flow valuation of Vinci SA, built from the FY2025 consolidated financial statements. Part of a three-company European Power, Utilities & Infrastructure (PUI) valuation portfolio — see [Portfolio](#portfolio) below.

Vinci is the anchor of the portfolio: it is the one name where a civil-engineering background maps directly onto the business, operating the same category of physical assets (roads, airports) it trains an engineer to design and build, under the concession-finance structure that infrastructure funds acquire.

---

## Headline output

| Terminal value method | Implied share price | vs. market (€126.90) |
|---|---|---|
| Gordon Growth perpetuity (g = 1.0%) | **€316.96** | +150% |
| Exit EV/EBITDA multiple (10.5×) | **€295.69** | +133% |

Both methods place implied value well above the traded price. This is treated as an **analytical finding, documented — not a target to force**. See [The finding](#the-finding).

![Vinci SA — valuation football field](assets/vinci_football_field.png)

---

## Methodology

Unlevered free cash flow (UFCF) build, explicit forecast FY2026–FY2030, WSP convention:

```
Revenue → EBITDA → EBIT → Tax on EBIT → NOPAT
  + D&A  + Δ Net working capital  − Capex  = UFCF
```

- **WACC** built with the CAPM and **net-debt** capital weights.
- **Terminal value** computed **both ways** (Gordon Growth and exit EV/EBITDA), each cross-checked against the other: the Growth-method TV backs out an implied exit multiple; the Exit-method TV backs out an implied growth rate.
- **Stub period + mid-year convention**: Year-1 UFCF prorated for the fraction of FY2026 remaining after the valuation date (~0.49); mid-year toggle on.
- **Reverse-DCF**: the current market price is inverted to recover the long-term growth rate the market is implying.

---

## Key assumptions & sources

Every hardcoded input carries a dated source comment in the workbook. The main ones:

| Input | Value | Source |
|---|---|---|
| Risk-free rate | 2.988% | ECB euro-area AAA bond yield curve, 10Y spot, 2 Jul 2026 |
| Beta | 0.75 | stockanalysis.com, DG.PA, 5Y monthly |
| Equity risk premium (France) | 5.01% | Damodaran Country Risk Premium dataset, 4 Jul 2026 |
| Pre-tax cost of debt | 4.4% | Vinci's own disclosed avg. cost of long-term gross financial debt, FY2025 |
| Long-run tax rate | 25.8% | French statutory rate (used for the perpetual WACC) |
| Explicit-period tax rate | 34.8% → 25.8% | French temporary large-company surtax, FY2025–26, reverting thereafter |
| Net debt | €19,075m | FY2025 consolidated financial statements, p.61 |
| Diluted shares | 530.01m | stockanalysis.com, 4 Jul 2026 |

**WACC = 5.98%** — cost of equity 6.75%, after-tax cost of debt 3.26%, weights 78.0% equity / 22.0% net debt.

One deliberate refinement worth flagging: France's temporary corporate surtax is applied **only in the explicit forecast tax schedule** (where it actually bites, FY2025–26), while the WACC — which discounts a perpetual stream — uses the long-run 25.8% rate. Applying the near-term surtax to a perpetuity would be a modelling error.

---

## The finding

The DCF implies ~+130–150% upside, which is large enough to demand an explanation rather than a headline. The reverse-DCF supplies it: at €126.90 the market is pricing a long-term growth rate of **−7.4%** — i.e. secular decline. That is not a plausible fundamental view of Vinci; it is the signature of a **CAPM limitation for low-beta infrastructure names**. A 0.75 beta produces a cost of equity that, combined with stable double-digit-margin concession cash flows, mechanically generates a high valuation. The gap is a property of the standard single-WACC CAPM approach applied to a long-duration, low-beta asset — documented as such, not patched by reverse-engineering the assumptions to hit the market price.

![Vinci SA — implied price sensitivity to WACC and long-term growth](assets/vinci_sensitivity_heatmap.png)

---

## What this model deliberately does not attempt

- **No segment-level WACC.** Vinci is valued as a single consolidated block at one WACC. This blends low-margin construction with high-margin motorway/airport concessions — a known simplification. A full sum-of-the-parts (as built for [Ferrovial](https://github.com/fcastillofadda/ferrovial-dcf)) would separate them.
- **No concession-maturity modelling.** Vinci Autoroutes' individual concession expiries are not modelled as a fixed-horizon amortisation; the terminal value uses a perpetuity.
- **No project-finance / non-recourse debt split.** Corporate and project-level debt are treated together in the net-debt bridge.

---

## Model integrity checks (all pass)

- Terminal value as % of enterprise value within the normal 60–90% range (81.3%)
- Implied exit multiple from the Growth method reasonable (<15×)
- Implied growth rate from the Exit-multiple method reasonable (0–4%)
- The two TV methods within 15% of each other
- Net debt ties to the Historicals reconciliation

---

## Portfolio

This is one of three standalone European PUI valuations, each in its own repo:

1. **Vinci SA** — construction + concessions *(this repo)*
2. [National Grid plc](https://github.com/fcastillofadda/national-grid-dcf) — regulated transmission utility (the "boring but correct" control case)
3. [Ferrovial N.V.](https://github.com/fcastillofadda/ferrovial-dcf) — toll roads + airports, with a full sum-of-the-parts extension

Together they cover three core corners of PUI coverage: the physical assets an engineer builds (Vinci), the regulated-utility core (National Grid), and multi-asset concessions valued sum-of-the-parts (Ferrovial).

---

## Sources

Vinci FY2025 Universal Registration Document and consolidated financial statements (IFRS); ECB and Damodaran for macro inputs; stockanalysis.com for market data. All figures in EUR millions unless noted.

## Disclaimer

An independent educational modelling exercise built from public filings. Not investment advice, not a price target, and not affiliated with Vinci SA.
