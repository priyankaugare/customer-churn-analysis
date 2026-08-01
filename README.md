# Customer Churn Analysis

Analysis of customer churn drivers for a telecom provider, using SQL and Python to identify which customer segments are most likely to cancel — and why.

## Dataset
[Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) — IBM Sample Data Sets (public, 7,043 customers, 21 attributes: demographics, account info, services subscribed, and churn status).

## Tools
Python (Pandas), SQL (SQLite), Matplotlib

## Approach
1. **Data cleaning** — coerced `TotalCharges` to numeric, dropped 11 rows with blank charges (all brand-new customers with 0 tenure).
2. **SQL analysis** (`churn_analysis.sql`) — aggregated churn rate across contract type, internet service, tenure, and combined risk segments.
3. **Visualization** — charted churn rate by contract, tenure, and service type.

## Key Findings
- **Overall churn rate: 26.6%** (1,869 of 7,032 customers).
- **Contract type is the strongest driver** — month-to-month customers churn at **42.7%**, vs **11.3%** for one-year and just **2.9%** for two-year contracts.
- **Fiber optic customers churn more than double DSL customers** (41.9% vs 19.0%), despite paying ~$33/month more on average — suggesting a price-to-value gap, not a service outage issue.
- **Churn is heavily front-loaded**: 47.7% of customers with under 12 months' tenure churn, dropping to 9.5% for customers past 4 years — retention efforts matter most in the first year.
- **Highest-risk segment**: month-to-month, fiber optic, paying by electronic check — this group alone churns at **60.4%**.

## Recommendation
Target retention offers (e.g., discounted 1-year contract upgrades) at new fiber optic customers on month-to-month plans within their first 12 months — this segment drives a disproportionate share of total churn.

## Files
- `Telco-Customer-Churn.csv` — source data
- `churn_analysis.sql` — SQL queries
- `churn_analysis.ipynb` — full Python analysis (cleaning, SQL via SQLite, charts)
- `charts/` — churn rate visualizations
