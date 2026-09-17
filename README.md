# 🚗 Ride-Hailing Platform: Q3 Revenue Drop Investigation

An end-to-end data analysis project investigating a **~19.1% net revenue drop** in Q3 2026 for a ride-hailing platform. Built using SQL (DuckDB/SQLite) and Python (Pandas, Matplotlib, Seaborn).

# Author: Lalu Zidane Alif Akbar

---

## 📌 Executive Summary

During Q3 2026, the platform experienced a sharp drop in total net revenue despite maintaining stable user demand. This investigation evaluates three potential business hypotheses to isolate the root cause and provide actionable recommendations.

![Dashboard Summary](dashboard_summary.png)

### Key Metrics Overview

| Metric | Q2 (Apr-Jun) | Q3 (Jul-Sep) | YoY / QoQ Change | Business Status |
| :--- | :--- | :--- | :--- | :--- |
| **Total Net Revenue** | **Rp190.33M** | **Rp153.87M** | **-19.15%** | 🔴 Critical Drop |
| **Active Users (MAU)** | 1,491 users | 1,486 users | **-0.33%** | 🟢 Stable |
| **Total Order Intents** | 7,459 orders | 7,541 orders | **+1.10%** | 🟢 High Demand |
| **Fulfillment Rate** | **82.41%** | **58.53%** | **-23.88%** | 🔴 Supply Issue |
| **Avg Pickup Wait Time** | **4.5 mins** | **16.0 mins** | **+11.5 mins** | 🔴 Service Degradation |
| **Driver Cancel Rate** | **4.56%** | **16.28%** | **+11.72%** | 🔴 High Friction |
| **Promo Usage Rate** | 54.58% | 18.06% | **-36.52%** | 🟡 Budget Cut |

---

## 🔍 Hypothesis-Driven Analysis

### ❌ Hypothesis 1: Volume Drop (Active Users Churn)
* **Premise:** Revenue dropped because users churned or migrated to competitors.
* **Finding:** **REJECTED.** Monthly Active Users remained virtually identical (~1,486 users), and total booking intents increased by **+1.10%** in Q3. Demand is strong.

### 🔑 Hypothesis 2: Behavior Drop (Operational Fulfillment Bottleneck)
* **Premise:** Revenue dropped because users experienced order failures due to driver supply issues.
* **Finding:** **CONFIRMED (Primary Root Cause).** 
  * Fulfillment rate collapsed from **82.41%** down to **58.53%**.
  * Average pickup wait time spiked from **4.5 minutes** to **16.0 minutes**.
  * Driver cancellation rate increased nearly 4x (from 4.56% to 16.28%).

### ⚠️ Hypothesis 3: Basket Size Drop (Promo Dependency & Discounts)
* **Premise:** Revenue dropped because users stopped ordering after marketing cut promo subsidies.
* **Finding:** **SECONDARY FACTOR.** Discount budgets were slashed from Rp45.9M to Rp15.0M. While this reduced promo usage from 54.58% to 18.06%, gross fares remained stable (~Rp37,100), proving that users were still willing to initiate orders without promos.

---

## 💡 Business Recommendations

1. **Driver Supply & Dispatch Optimization:** Re-evaluate driver density and allocation algorithms to reduce pickup wait times back below the 5-minute threshold.
2. **Driver Retention & Incentive Alignment:** Address driver cancellations by introducing short-distance completion bonuses during peak hours.
3. **Targeted Promo Allocation:** Shift from mass discounting to targeted retention promos focused on high-value users experiencing long wait times.

---

## 🚀 How to Run locally
# Clone the repository
git clone [https://github.com/Zidane703/ride-hailing-revenue-drop-analysis.git](https://github.com/Zidane703/ride-hailing-revenue-drop-analysis.git)

# Navigate to project folder
cd ride-hailing-revenue-drop-analysis

# Install requirements
pip install pandas matplotlib seaborn duckdb



## 🛠️ Project Structure

```text
├── users.csv               # Customer profiles, registration dates, & acquisition channels
├── orders.csv              # 15,000 transaction records with pricing & operational metrics
├── dashboard_summary.png   # Visualization chart generated via Matplotlib/Seaborn
└── README.md               # Project documentation

