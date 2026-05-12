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

## Client Context: Global Horizon Agency

This data architecture and reporting solution was developed for **Global Horizon Agency**, a digital marketing firm managing high-volume ad campaigns across digital platforms.

**The Business Problem:**
Previously, the agency relied on fragmented, platform-specific CSV exports to track performance. This siloed approach made it impossible to accurately compare cross-channel efficiency or calculate true Cost Per Engagement at the macro level.

**The Solution:**
By designing a centralized reporting pipeline and an interactive executive dashboard, Global Horizon leadership can now monitor core metrics like Cost Per Engagement and Weighted Conversion Rates in real-time. This allows stakeholders to quickly identify underperforming campaigns and confidently reallocate marketing budgets based on mathematically sound data models.

---


## Project Summary

This project delivers an end-to-end **Campaign Cost & Conversion Performance Dashboard** designed to evaluate campaign efficiency, audience engagement, and overall return on ad spend across multiple digital channels. 

The solution bypasses standard spreadsheet limitations by utilizing an enterprise-grade business intelligence workflow. Raw marketing data was ingested via Power Query, where rigorous data quality assurance was performed to establish a clean, refined dataset prior to modeling. The data was then structured into a robust Star Schema within Power Pivot. 

To ensure mathematical accuracy across all dynamic filter contexts, complex ratio metrics (such as Cost Per Engagement) and weighted conversion rates were explicitly programmed using DAX. The final output is a fully interactive, dark-themed user interface with locked-down navigation, providing stakeholders with a seamless, application-like experience to uncover actionable marketing insights.

**Key Technologies:** 
Excel, Power Query (ETL & QA), Power Pivot (Star Schema Data Modeling), DAX (Advanced Aggregations), UI/UX Design.


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

![Data Model - Star Schema](https://raw.githubusercontent.com/zulfqara/End-to-End-Campaign-Cost-and-Conversion-Performance/main/Data%20Model%20Diagram%20-%20Digital%20Marketing.png)

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

##  Dataset Source:
    The dataset was sourced from Kaggle: ![Digital Marketing Campaigns for SMEs](https://www.kaggle.com/datasets/farhanmittho/digital-marketing-campaigns-for-smes)

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/iamzulfiqarali)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/zulfqara)

</div>
