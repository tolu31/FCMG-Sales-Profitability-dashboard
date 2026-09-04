# FMCG Sales & Profitability Intelligence Dashboard

**Identifying revenue and profitability opportunities across products, regions, channels, and campaigns for an FMCG business — built end-to-end in Excel with Power Query, Pivot Tables, and an interactive KPI dashboard.**

![Excel](https://img.shields.io/badge/Tool-Excel-217346?logo=microsoft-excel&logoColor=white)
![Power Query](https://img.shields.io/badge/Tool-Power%20Query-2C5E77)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📌 Business Objective

Identify opportunities to increase revenue and profitability in an FMCG business.

**Primary Question:** Which products, customers, regions, channels and campaigns should management prioritize?

**Deliverables:** Clean dataset · Analytical workbook · KPI dashboard · Evidence-based recommendations

---

## 


🗂️ Dataset

- **100,000+ transaction-level records** covering Jan 2025–Jun 2026
- 25 fields spanning sales (Product, Category, Region, Sales_Channel), financials (Revenue, Cost, Profit, Discount), customer data (Customer_Segment), and marketing (Campaign, Impressions, Clicks, Leads, Purchases, Marketing_Spend)
- Raw data intentionally contained realistic data-quality issues (duplicates, missing values, inconsistent formatting, invalid entries) to simulate a real-world cleaning task

---

## 🛠️ Tools & Skills Demonstrated

| Area | Tools / Techniques |
|---|---|
| Data Cleaning | Power Query (Excel) — deduplication, text standardization, lookup-based recovery, calculated columns, data-quality flagging |
| Analysis | PivotTables, calculated fields, campaign ROI/ROAS, funnel conversion analysis |
| Visualization | PivotCharts, conditional-formatting heatmaps, slicers, KPI cards |
| Documentation | Data dictionary, cleaning log with rationale for every treatment decision |

---

## 🧹 Data Cleaning Summary

| Issue | Records Affected | Treatment |
|---|---|---|
| Exact duplicate rows | 120 (234 rows) | Removed via Transaction_ID |
| Inconsistent text formatting (Region, Product, City, Channel, Campaign) | ~all rows | Trimmed, cleaned, standardized casing |
| Missing Region | 45 | Recovered via City → Region lookup (fully deterministic, not estimated) |
| Missing Customer_Segment | 25 | Labeled "Unknown" — not deleted |
| Invalid/placeholder Date entries | 25 | Nulled ("TBD" and a repeating impossible date, both identified as system placeholders, not typos) |
| Revenue anomalies | 42 (7 sentinel + 35 missing) | Sentinel value nulled; missing values recalculated from Units_Sold × Unit_Price × (1 − Discount) |
| Missing Marketing_Spend | 30 | Imputed using campaign-level median |
| Logical inconsistency (Units_Sold = 0, Revenue > 0) | 8 | Flagged for review, not deleted |

Full reasoning for every decision is documented in the workbook's cleaning log — **no records were deleted without investigation**, per the project brief.

---

## 📊 Dashboard Preview

![Dashboard Screenshot](assets/<img width="1920" height="1080" alt="Dashboard" src="https://github.com/user-attachments/assets/755682b8-b487-400b-984a-e8bd9e934aae" />
)

*Replace `assets/dashboard.png` with your actual dashboard screenshot before publishing.*

The dashboard includes:
- KPI cards: Total Revenue, Total Profit, Total Marketing Spend, Average Profit Margin
- Revenue & Profit by Product
- Profit by Category & Region
- ROAS by Campaign
- Revenue & Profit by Customer Segment
- Monthly Revenue & Profit Trend
- ROAS by Sales Channel
- Interactive slicers (Region, Category, Campaign, Date) connected across all visuals

---

## 🔎 Key Findings

- **Products:** Hair Cream, Body Lotion, and Ozone Shampoo are the top three profit drivers; Bath Soap consistently underperforms.
- **Regions:** Lagos generates disproportionately more profit than any other region, followed by Ogun.
- **Campaigns:** Campaign C delivers the highest ROI among paid campaigns. Organic traffic alone generated ~₦49.3M in revenue at zero marketing spend.
- **Channels & Segments:** Profit margin is largely flat across Sales_Channel and Customer_Segment (49.6%–51.1%) — **except Distributor**, which is consistently ~1.3 points lower than every other channel, across every customer segment.
- **Marketing Funnel:** Click-through, lead conversion, and purchase conversion rates are nearly identical across all four paid campaigns — the real differentiator between campaigns is reach (impressions), not funnel efficiency.

---

## ✅ Recommendations

1. Prioritize Hair Cream, Body Lotion, and Ozone Shampoo in inventory and promotional planning; review Bath Soap's cost/pricing structure.
2. Direct incremental investment toward Lagos and Ogun; investigate growth barriers in lower-performing regions like Enugu.
3. Reallocate marketing budget toward Campaign C; investigate whether Organic's zero-cost performance can be scaled.
4. Investigate the Distributor channel's persistent margin and ROAS gap — the pattern holds across every customer segment, pointing to a channel-level cost or discount issue rather than a customer-mix problem.
5. Since funnel conversion is consistent across campaigns, prioritize scaling reach over further creative/targeting optimization.
6. Resolve the 8 flagged Units_Sold = 0 / Revenue > 0 records with the data owner to confirm root cause.

---

## 📁 Repository Structure
├── FMCG_Sales_Profitability_Intelligence_Dataset.xlsx # Full project workbook:
│ # - Raw_Data (untouched source)
│ # - Worksheet / Worksheet_Clean (Power Query pipeline)
│ # - Pivot_Analysis (supporting pivot tables)
│ # - Dashboard (KPI dashboard)
│ # - Data Cleaning Process (documentation)
│ # - Findings & Recommendations (documentation)
├── assets/
│ └── dashboard.png # Dashboard screenshot
└── README.md

---

## 🚀 How to Use

1. Download `FMCG_Sales_Profitability_Intelligence_Dataset.xlsx`
2. Open in Excel and go to **Data → Queries & Connections → Refresh All** to re-run the full cleaning pipeline from raw data
3. Explore the `Pivot_Analysis` and `Dashboard` sheets, or use the slicers to filter by Region, Category, Campaign, or Date
4. See the `Data Cleaning Process` and `Findings & Recommendations` sheets within the same workbook for full documentation

---

## 👤 About

Built as a portfolio project to demonstrate end-to-end data analysis: investigating and documenting data quality issues, building a reproducible cleaning pipeline in Power Query, deriving business insights through pivot analysis, and communicating findings through an interactive dashboard and evidence-based recommendations.

**Connect with me:** [LinkedIn](#) · [Portfolio Website](#)
