<div align="center">

# <img src="https://raw.githubusercontent.com/zulfqara/End-to-End-Campaign-Cost-and-Conversion-Performance/main/Global%20Horizon%20-%20Logo.png" align="absmiddle" width="45"> Global Horizon Agency
## Campaign Cost & Conversion Performance Dashboard

[![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)](https://www.microsoft.com/excel)
[![Power Query](https://img.shields.io/badge/Power_Query-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://docs.microsoft.com/power-query)
[![Power Pivot](https://img.shields.io/badge/Power_Pivot-217346?style=for-the-badge&logo=microsoft&logoColor=white)](https://docs.microsoft.com/power-pivot)
[![DAX](https://img.shields.io/badge/DAX-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://docs.microsoft.com/dax)

![Dashboard Preview](https://github.com/zulfqara/End-to-End-Campaign-Cost-and-Conversion-Performance/blob/main/Dashboard-DM.png)

</div>

---

## 🛠️ Skills Demonstrated

| Category | Skills |
|---|---|
| **Data Transformation** | Power Query · ETL · Data Type Standardization · Custom Column Engineering |
| **Data Modeling** | Star Schema · Power Pivot · Table Relationships · Medallion Architecture |
| **Calculations** | DAX Measures · DIVIDE · SUMX · Weighted Aggregation |
| **Visualization** | Excel Dashboard Design · Combo Charts · Slicers · KPI Cards |
| **Analytics** | Cost Efficiency Analysis · Conversion Analysis · Dimensional Analysis |

---

## 📊 Project Overview

**Domain:** Digital Marketing Analytics
**Dataset:** 1,000 campaigns across 5 platforms, 7 industries, 5 global regions
**Deliverable:** Interactive Excel dashboard analyzing campaign cost efficiency and conversion performance across platforms, demographics, and campaign durations

---

## 🏗️ Technical Implementation

### Data Pipeline — Medallion Architecture
```
🟤 Bronze  →  Raw CSV ingestion into Power Query
⚪ Silver  →  Cleaning · Standardization · Column Engineering
🟡 Gold    →  Star Schema · DAX Measures · Dashboard
```

## Data Model:

![Data Model - Star Schema]([https://github.com/zulfqara/End-to-End-Campaign-Cost-and-Conversion-Performance/blob/main/Dashboard-DM.png](https://github.com/zulfqara/End-to-End-Campaign-Cost-and-Conversion-Performance/blob/main/Data%20Model%20Diagram%20-%20Digital%20Marketing.png))

### Key Engineering Decisions

**1. Ratio Metrics as DAX Measures — Not Power Query Columns**

> All ratio KPIs (CPE, CPU) are DAX measures to ensure mathematically correct aggregation across every filter context. Pre-calculating ratios row-by-row produces incorrect totals when aggregated.

**2. Weighted Conversion Rate**

> `AVERAGE([conversion_rate])` was intentionally avoided. Each platform manages unequal campaign volumes, making a simple average statistically misleading. A weighted average using `audience_reach` as the weighting factor was applied instead.

```dax
Weighted Conversion Rate =
DIVIDE(
    SUMX(fact_campaigns, [conversion_rate] * [audience_reach]),
    SUM(fact_campaigns[audience_reach])
)

Cost Per Engagement =
DIVIDE(SUM([ad_spend]), SUM([engagement_metric]))

Cost Per User =
DIVIDE(SUM([ad_spend]), SUM([audience_reach]))
```

## 🔍 Key Findings

- **Email CPA anomaly:** Email's CPA ($26.50) is 260x higher than Social Media ($0.09), despite comparable CPE and conversion rates — signaling a niche but high-cost audience
- **Top reach engine:** Social Media drives the highest engagement volume (495.9M) at the lowest CPA ($0.09)
- **Equal spend distribution:** Average ad spend is nearly uniform across all platforms (~$27K), confirming the agency currently allocates budget equally rather than performance-weighted

---

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/iamzulfiqarali)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/zulfqara))

</div>
