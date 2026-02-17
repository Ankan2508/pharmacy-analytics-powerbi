# 💊 Pharmacy Sales & Profitability Analytics

> **Onyx Data Challenge — January / February 2026**  
> A full end-to-end Power BI report covering 120 European pharmacies, 220 products, and €8.6M in revenue.

![Power BI](https://img.shields.io/badge/Power%20BI-Report-0F766E?style=flat-square&logo=powerbi)
![DAX](https://img.shields.io/badge/DAX-64%20Measures-14B8A6?style=flat-square)
![HTML Visuals](https://img.shields.io/badge/HTML%20Visuals-8%20Cards-2DD4BF?style=flat-square)
![Pages](https://img.shields.io/badge/Report%20Pages-4-F59E0B?style=flat-square)

---

## 📁 Repository Structure

```
pharmacy-analytics-powerbi/
│
├── 01_data/
│   ├── Pharmacy_Data_Challenge_Dataset.xlsx    # Raw dataset (62,139 transactions)
│   ├── data_dictionary.md                      # Field descriptions for all tables
│   └── schema_diagram.png                      # Star schema visual
│
├── 02_report/
│   ├── Pharmacy_Analytics.pbix                 # Main Power BI report
│   └── Pharmacy_Analytics_Report_Design.docx   # Full design specification
│
├── 03_dax/
│   ├── Pharmacy_DAX_Measures_TMDL.docx         # 64 measures in TMDL format
│   └── html_measures/
│       ├── HTML_KPI_Cards_All_4.docx            # Flip-card KPIs (340×190px each)
│       ├── Dynamic_Key_Insights_Measure.docx    # Page 3 insight narrative card
│       ├── Promo_Insight_Card_HTML_DAX.docx     # Promo impact card (338×205px)
│       └── Strategic_Recommendations_HTML_DAX.docx  # Rec strip (1573×153px)
│
├── 04_page_previews/
│   ├── pharmacy_page1.html                     # The European Pharmacy Landscape
│   ├── pharmacy_page2.html                     # Markets & Margins
│   ├── pharmacy_page3_revised.html             # What Drives Profitability
│   └── pharmacy_page4.html                     # Promotional & Brand Strategy
│
├── 05_guides/
│   ├── Alert_Section_Implementation_Guide.docx
│   ├── Alert_Section_Tutorial_Helper.docx
│   ├── Page3_Page4_Implementation_Guide.docx
│   └── Navigation_Helper_Elements.docx
│
├── 06_assets/
│   ├── KPI.svg                                 # KPI card design reference
│   ├── Side_Panel.svg
│   └── screenshots/
│       ├── page1_overview.png
│       └── page2_markets.png
│
├── README.md
├── CHANGELOG.md
└── LICENSE
```

---

## 📊 Dataset Overview

| Metric | Value |
|--------|-------|
| Total Transactions | 62,139 |
| Pharmacies | 120 across 8 countries |
| Products | 220 across 5 categories |
| Time Period | 2024–2025 |
| Total Revenue | €8.6M |
| Gross Margin | €2.4M (28.0%) |
| Total Cost | €6.2M |

**Countries:** Germany · France · Italy · Belgium · Netherlands · Spain · Poland · Austria

**Categories:** OTC · Prescription · Personal Care · Wellness · Medical Devices

---

## 📄 Report Pages

### Page 1 — The European Pharmacy Landscape
Network performance overview. KPI flip-cards, geographic map, network composition breakdown (Urban/Suburban/Rural), monthly revenue/margin/cost trend toggle, and product category donut chart.

### Page 2 — Markets & Margins
Geographic deep-dive. Country performance table with donut indicators, profitability patterns scatter plot, revenue by region bar chart, performance by location type, and the **Underperformer Alert section** (auto-flags pharmacies with margin < 20% or negative YoY growth).

### Page 3 — What Drives Profitability
Category analysis. Full-width performance matrix with progress bars and growth badges, Top 10 products by margin, portfolio balance bubble chart, and a **dynamic insight card** that auto-generates strategic narrative from live data.

### Page 4 — Promotional & Brand Strategy
Profitability driver deep-dive. Promotional impact comparison (promoted vs. regular sales), generic vs. branded performance, and a **dynamic strategic recommendations strip** (1573×153px) with 4 data-driven recommendation cards.

---

## ⚙️ DAX Measures — What's Included

All 64 measures are in copy-paste ready **TMDL format** in `03_dax/Pharmacy_DAX_Measures_TMDL.docx`.

| Category | Measures |
|----------|----------|
| Core KPIs | `total_revenue`, `total_margin`, `margin_percent`, `total_cost`, `transaction_count` |
| Time Intelligence | `py_revenue`, `yoy_revenue_growth`, `yoy_margin_growth`, `mtd_revenue`, `qtd_revenue`, `ytd_revenue`, `revenue_cagr` |
| Geographic | `pharmacy_count`, `avg_revenue_per_pharmacy`, `urban_pharmacy_count`, `suburban_pharmacy_count`, `rural_pharmacy_count` |
| Promotional | `promo_revenue`, `non_promo_revenue`, `promo_margin_percent`, `non_promo_margin_percent`, `promo_margin_impact` |
| Brand | `generic_revenue`, `branded_revenue`, `generic_margin_percent`, `branded_margin_percent` |
| Alert Logic | `is_underperformer`, `primary_issue`, `margin_status_color`, `yoy_growth_color`, `no_issues_message` |
| HTML Visuals | `html_card_total_revenue`, `html_card_total_margin`, `html_card_total_cost`, `html_card_transaction_volume`, `html_key_insights_page3`, `html_promo_insight_card`, `html_strategic_recommendations` |
| Tutorial | `tutorial_navigation_pane`, `tutorial_kpi_cards`, `tutorial_filter_reset`, `tutorial_chart_toggles`, `tutorial_alert_section` |

---

## 🌐 HTML-Based DAX Visuals

All HTML visuals are rendered via the **HTML Content** custom visual and are 100% driven by live DAX calculations.

| Visual | Size | Page | Description |
|--------|------|------|-------------|
| `html_card_total_revenue` | 340×190px | P1 | Teal flip-card, hover reveals analysis |
| `html_card_total_margin` | 340×190px | P1 | Green flip-card, margin health narrative |
| `html_card_total_cost` | 340×190px | P1 | Amber flip-card, cost ratio analysis |
| `html_card_transaction_volume` | 340×190px | P1 | Blue flip-card, volume velocity insight |
| `html_key_insights_page3` | Full width | P3 | Dynamic category insight narrative |
| `html_promo_insight_card` | 338×205px | P4 | Severity-adaptive promotional alert |
| `html_strategic_recommendations` | 1573×153px | P4 | 4-column recommendation strip |
| `tutorial_alert_section` | ~350px | P2 | Alert section explainer overlay |

---

## 🚀 Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/pharmacy-analytics-powerbi.git

# 2. Open in Power BI Desktop
# File > Open > Pharmacy_Analytics.pbix

# 3. Set data source path
# Transform Data > Data Source Settings > update path to 01_data/

# 4. Preview pages in browser (no Power BI needed)
open 04_page_previews/pharmacy_page1.html
```

### Requirements
- Power BI Desktop (March 2024 or later)
- [HTML Content visual](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380732) from AppSource (for HTML card measures)
- Microsoft Excel (to view raw dataset)

---

## ✨ Standout Features

- **Flip-card KPI visuals** — Apple-style hover animations revealing CAGR, YoY, and period growth
- **Dynamic insight narratives** — Pure DAX generates intelligent paragraph text that adapts to filters
- **Severity-adaptive promo card** — Icon, color, and recommendation text change based on impact severity (⛔ Critical → ⚠️ Significant → ⚡ Moderate)
- **1573px recommendation strip** — All 4 cards data-driven; updates with country/year slicers
- **Underperformer alert** — Auto-detects and flags pharmacies using SWITCH/OR logic; empty-state handler shows success message
- **Full TMDL format** — Compatible with Tabular Editor 2 and 3
- **Interactive HTML prototypes** — All 4 pages previewable in any browser, no Power BI needed

---

## 🎨 Design System

Inspired by **Ruxandra Vilău** (Power BI DataViz World Championships winner).

| Token | Value | Usage |
|-------|-------|-------|
| Primary | `#0F766E` | Headers, active states, icons |
| Teal Mid | `#14B8A6` | Secondary elements |
| Teal Light | `#2DD4BF` | Accents, chart fills |
| Alert Amber | `#F59E0B` | Warnings, promotional theme |
| Alert Red | `#DC2626` | Critical flags |
| Success Green | `#10B981` | Positive performance |
| Body Text | `#374151` | All body copy |

**Typography:** Segoe UI (report), Courier New (DAX code), -apple-system / BlinkMacSystemFont (HTML visuals)

---

## 📝 License

MIT License — free to use, adapt, and share with attribution.

---

*Built by **Ankan Bandyopadhyay** · Onyx Data Challenge · January / February 2026*  
*Design inspiration: Ruxandra Vilău · Power BI DataViz World Championships*
