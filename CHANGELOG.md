# Changelog

All notable changes to this project are documented here.

---

## [1.0.0] — 2026-02-17 · Initial Release

### Added — Report
- Page 1: The European Pharmacy Landscape (KPIs, map, network composition, trend chart, product donut)
- Page 2: Markets & Margins (country table, scatter plot, region bars, location type cards, underperformer alert)
- Page 3: What Drives Profitability (category matrix, top 10 products, portfolio bubble chart, insight card)
- Page 4: Promotional & Brand Strategy (promo comparison, generic vs. branded, strategic recommendations)

### Added — DAX Library
- 64 measures in TMDL format across 8 categories
- Core KPIs: `total_revenue`, `total_margin`, `margin_percent`, `total_cost`, `transaction_count`, `total_units_sold`
- Time intelligence: YoY, CAGR, MTD, QTD, YTD, prior year comparisons
- Geographic: urban/suburban/rural breakdowns, per-pharmacy averages
- Promotional: promo vs. non-promo revenue, margin, units, impact
- Brand: generic vs. branded counts, revenue, margin
- Alert: `is_underperformer`, `primary_issue`, color helpers, empty-state message
- Performance: ranking, underperformer detection, moving averages

### Added — HTML Visual Measures
- 4× KPI flip-cards (340×190px): Revenue (teal), Margin (green), Cost (amber), Transactions (blue)
- Dynamic Key Insights card for Page 3 (auto-generates category narrative)
- Promotional Impact card for Page 4 (338×205px, severity-adaptive)
- Strategic Recommendations strip for Page 4 (1573×153px, 4 dynamic cards)

### Added — Tutorial / Navigation Helpers
- Navigation pane explainer
- KPI cards explainer
- Filter & Reset buttons explainer
- Line chart toggle explainer
- Alert section explainer (with criteria, color codes, drill-through tip)

### Added — Implementation Guides
- Alert section step-by-step guide (8 steps, conditional formatting, drill-through, tooltips)
- Pages 3 & 4 implementation guide
- Navigation helper elements guide

### Added — Interactive Prototypes
- pharmacy_page1.html — European Pharmacy Landscape
- pharmacy_page2.html — Markets & Margins
- pharmacy_page3_revised.html — What Drives Profitability
- pharmacy_page4.html — Promotional & Brand Strategy

---

*Pharmacy Analytics · Onyx Data Challenge · 2026*
