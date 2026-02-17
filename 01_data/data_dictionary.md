# Data Dictionary

> Pharmacy Sales & Profitability Analytics · Onyx Data Challenge 2026

---

## Tables

### FactSales
The central fact table contains one row per transaction.

| Column | Type | Description |
|--------|------|-------------|
| `SaleID` | Integer | Unique transaction identifier |
| `PharmacyID` | Integer | FK → DimPharmacy |
| `ProductID` | Integer | FK → DimProduct |
| `DateID` | Integer | FK → DimDate |
| `RevenueEUR` | Decimal | Sale revenue in Euros |
| `CostEUR` | Decimal | Cost of goods sold in Euros |
| `MarginEUR` | Decimal | Gross margin in Euros (Revenue − Cost) |
| `UnitsSold` | Integer | Number of units sold |
| `IsPromotional` | Boolean | 1 = promotional sale, 0 = regular sale |

---

### DimPharmacy
One row per pharmacy location.

| Column | Type | Description |
|--------|------|-------------|
| `PharmacyID` | Integer | Primary key |
| `PharmacyName` | Text | Pharmacy name |
| `Country` | Text | Country of operation |
| `Region` | Text | Sub-national region (e.g., Lombardy, Hamburg) |
| `LocationType` | Text | Urban / Suburban / Rural |
| `Latitude` | Decimal | Geographic coordinate |
| `Longitude` | Decimal | Geographic coordinate |

**Distribution:**
- Urban: 50 pharmacies (42%)
- Suburban: 47 pharmacies (39%)
- Rural: 23 pharmacies (19%)

**Countries:** Germany (22), France (20), Italy (18), Belgium (14), Netherlands (11), Spain (12), Poland (13), Austria (10)

---

### DimProduct
One row per product SKU.

| Column | Type | Description |
|--------|------|-------------|
| `ProductID` | Integer | Primary key |
| `ProductName` | Text | Product name |
| `Category` | Text | OTC / Prescription / Personal Care / Wellness / Medical Devices |
| `IsGeneric` | Boolean | 1 = generic, 0 = branded |

**Portfolio:**
- Total SKUs: 220
- Generic: 33 (15%)
- Branded: 187 (85%)

**Category breakdown (revenue share):**
- Prescription: 32.4% — 63,277 units, 21.9% margin
- OTC: 20.8% — 177,686 units, 29.4% margin
- Wellness: 19.5% — 89,423 units, 33.6% margin
- Personal Care: 16.8% — 101,510 units, 33.5% margin
- Medical Devices: 10.1% — 13,897 units, 25.0% margin

---

### DimDate
Standard date dimension table.

| Column | Type | Description |
|--------|------|-------------|
| `DateID` | Integer | Primary key (YYYYMMDD) |
| `Date` | Date | Full date value |
| `Year` | Integer | Calendar year |
| `Quarter` | Integer | Quarter (1–4) |
| `Month` | Integer | Month number (1–12) |
| `MonthName` | Text | Month name (January, February, …) |
| `YearMonth` | Text | YYYY-MM format |
| `IsWeekend` | Boolean | 1 = Saturday or Sunday |

**Period covered:** 2024–2025 (2 full years)

---

## Key Business Metrics

| Metric | Value | Formula |
|--------|-------|---------|
| Total Revenue | €8.6M | `SUM(FactSales[RevenueEUR])` |
| Total Margin | €2.4M | `SUM(FactSales[MarginEUR])` |
| Overall Margin % | 28.0% | `[total_margin] / [total_revenue]` |
| Total Cost | €6.2M | `SUM(FactSales[CostEUR])` |
| Transactions | 62,139 | `COUNT(FactSales[SaleID])` |
| Units Sold | 445,793 | `SUM(FactSales[UnitsSold])` |
| Avg Revenue / Pharmacy | ~€71.7K | `[total_revenue] / [pharmacy_count]` |

---

## Alert Thresholds

| Condition | Threshold | Flag |
|-----------|-----------|------|
| Low Margin | < 20% | Underperformer |
| Declining Revenue | YoY Growth < 0% | Underperformer |
| Critical Margin | < 15% | Red (#DC2626) |
| Warning Margin | 15–19.9% | Amber (#F59E0B) |
| Healthy Margin | ≥ 20% | Green (#10B981) |

---

*Data Dictionary · Pharmacy Analytics · Onyx Data Challenge · 2026*
