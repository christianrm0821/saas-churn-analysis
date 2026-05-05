# SaaS Subscription & Churn Analysis

## Overview
This case study analyzes a SaaS company's subscription and churn data across **500 accounts** and **5,000 subscriptions** to identify the key drivers of customer churn and surface actionable insights for retention strategy.

The analysis examines churn from multiple angles — plan tier, reason code, industry segment, support quality, and feature usage — to build a layered understanding of why customers leave and what can be done to retain them.

## Business Questions
1. Which customer segments are churning at the highest rates, and what reasons are driving them to leave?
2. Are there early warning signals — such as plan downgrades or declining feature usage — that predict churn before it happens?
3. What actionable recommendations can reduce churn and improve retention across key segments?

## Dataset
The analysis uses five interconnected tables from a Kaggle dataset ([SaaS Subscription & Churn Analytics](https://www.kaggle.com/datasets/rivalytics/saas-subscription-churn-analytics)):

| Table | Rows | Description |
|-------|------|-------------|
| **Accounts** | 500 | Unique companies with industry, plan tier, and churn status |
| **Subscriptions** | 5,000 | Subscription records with MRR, ARR, and churn flags |
| **Churn Events** | 600 | Churn records including reason codes and customer feedback |
| **Feature Usage** | 25,000 | Usage logs tracking feature engagement and error counts |
| **Support Tickets** | 2,000 | Customer support interactions with resolution times and satisfaction scores |

## Key Findings

### Plan Tier Does Not Drive Churn Rate
- Subscription-level churn rates are nearly identical across Basic (9.49%), Pro (9.67%), and Enterprise (9.98%)
- Account-level churn rates confirm the same pattern: Basic (22.02%), Pro (21.91%), Enterprise (22.08%)
- However, **churn reasons differ meaningfully by tier** — Basic customers cite support more often, while Pro and Enterprise customers are driven by budget and pricing concerns

### Cost Is the Biggest Churn Driver
- When combining budget and pricing reason codes, cost-related churn accounts for roughly **1 in 3** churned subscriptions
- Pro (~40%) and Enterprise (~35%) subscribers who churned disproportionately cited price as their reason
- This challenges the assumption that lower-tier customers feel more price pressure

### DevTools Is the Highest-Risk Industry
- DevTools has the highest account churn rate at **30.97%** (35 out of 113 accounts)
- Combined budget and pricing churns for DevTools alone (15 accounts) exceed total known-reason churns for any other single industry
- DevTools customers churn due to multiple compounding reasons — budget, support, and features

### Significant Data Quality Gap
- "No recorded reason" is the largest single churn category across all industries (35 out of 110 churned accounts)
- FinTech has the worst data gap: **48%** of churned accounts (12 out of 25) have no recorded reason
- This limits the ability to draw confident conclusions about churn drivers in several segments

### Support Quality Is Not a Measurable Churn Driver
- Resolution time, first response time, satisfaction score, and ticket count are nearly identical across all three plan tiers
- Churned accounts actually had slightly **better** support metrics than retained accounts
- Basic churned accounts had faster first response times (82.13 min vs 86.99 min) and higher satisfaction scores (4.08 vs 3.99) than Basic accounts that stayed

## Tools & Technologies
- **Python** — Pandas, NumPy, Matplotlib, Seaborn
- **Jupyter Notebook** — Analysis and visualization
- **Excel** — Executive summary dashboard and pivot tables *(planned)*
- **PowerPoint** — Stakeholder presentation *(planned)*

## Project Structure
```
saas-churn-analysis/
├── README.md
├── saas_case_study.ipynb          # Main analysis notebook
└── saas_case_study_datasets/
    ├── ravenstack_accounts.csv
    ├── ravenstack_churn_events.csv
    ├── ravenstack_feature_usage.csv
    ├── ravenstack_subscriptions.csv
    └── ravenstack_support_tickets.csv
```


## Recommendations Summary
1. **Improve churn data collection** — Incentivize churned accounts to record reasons for leaving, particularly in FinTech and HealthTech segments
2. **Address DevTools pricing** — Introduce personalized pricing tiers and conduct surveys to distinguish between affordability and perceived value problems
3. **Investigate the Basic tier support perception gap** — Conduct exit surveys to understand why Basic customers cite support despite similar measured metrics
4. **Develop features for FinTech and EdTech** — Both segments cite missing features as a top churn reason

## Status
🟢 Complete: Data cleaning, plan tier analysis, churn reason analysis, industry analysis, support ticket analysis  
🟡 In Progress: Feature usage analysis, downgrade early warning analysis  
🔴 Planned: SQL section, Excel dashboard, PowerPoint presentation

## Author
Christian Tapia
