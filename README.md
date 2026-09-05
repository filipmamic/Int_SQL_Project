# Intermediate SQL - Sales Analysis

## Overview
Analyzed customer behavior, retention, and lifetime value using SQL and data analysis techniques to uncover customer trends, identify retention opportunities, and support revenue growth for an e-commerce company.

## Business Questions
1. **Customer Segmentation:** Who are our most valuable customers?
2. **Cohort Analysis:** How do different customer groups generate revenue?
3. **Retention Analysis:** Who has not purchased recently?

## Analysis Approach

### 1. Customer Segmentation
- Categorized customers based on total lifetime value (LTV)
- Assigned customers to High, Mid, and Low-value segments
- Calculated key metrics: total customer LTV

Query: [1_customer_segmentation.sql](/1_customer_segmentation.sql)

**Visualization:**
![Customer Segmentation](/images/1_customer_segmentation.png)

**Key Findings:**
- High-value segment (25% of customers) drives 66% of total revenue ($135.6M)
- Mid-value segment (50% of customers) drives 32% of total revenue ($66.4M)
- Low-value segment (25% of customers) drives 2% of total revenue ($4.3M)

**Business Insights:**
- **High-Value (66% Revenue):** Offer a premium membership program to 12,372 VIP customers, as losing one customer significantly impacts revenue
- **Mid-Value (32% Revenue):** Create upgrade paths through personalized promotions with potential $66.4M → $135.6M revenue opportunity
- **Low-Value (2% Revenue):** Design re-engagement campaigns and price-sensitive promotions to increase purchase frequency

### 2. Cohort Analysis
- Tracked revenue and customer count per cohort
- Cohorts were grouped by year of first purchase
- Analyzed customer retention at a cohort level

Query: [2_cohort_analysis.sql](/images/2_cohort_analysis.png)

**Visualization:**
![Cohort Analysis](/images/2_cohort_analysis.png)

**Key Findings:**
- Revenue per customer shows an alarming decreasing trend over time
- 2022-2024 cohorts are consistently performing worse than earlier cohorts
- NOTE: Although net revenue is increasing, this is likely due to a larger customer base, which is not reflective of customer value

**Business Insights:**
- Value extracted from customers is decreasing over time, needs further investigation.
- In 2023, we saw a drop in the number of customers acquired, which is concerning.
- With both lowering LTV and decreasing customer acquisition, the company is facing potential revenue decline.

### 3. Retention Analysis
- Identified customers at risk of churning
- Analyzed last purchase patterns
- Calculated customer-specific metrics

Query: [3_retention_analysis.sql](/3_retention_analysis.sql)

**Visualization:**
![Customer Churn by Cohort Year](/images/3_customer_churn_cohort_year.png)

**Key Findings:**
- Cohort churn stabilizes at around 90% after 2-3 years, indicating a predictable long-term retention pattern.
- Retention rates are consistently low (8-10%) across all cohorts, suggesting retention issues are systemic rather than specific to certain years.
- Newer cohorts (2022-2023) show similar churn trajectories, signaling that without intervention, future cohorts will follow the same pattern.

**Business Insights:**
- Strengthen early engagement strategies to target the first 1-2 years with onboarding incentives, loyalty rewards, and personalized offers to improve long-term retention.
- Re-engage high-value churned customers by focusing on targeted win-back campaigns rather than broad retention efforts, as reactivating valuable users may yield higher ROI.
- Predict & preempt churn risk and use customer-specific warning indicators to proactively intervene with at-risk users before they lapse.

## Strategic Recommendations
- **Focus on high-value customers:** Build a VIP loyalty program with exclusive benefits and personalized offers to retain customers who generate the majority of the revenue.
- **Improve customer retention:** Strengthen onboarding, loyalty rewards, and personalized offers, especially during the first 1–2 years of the customer relationship.
- **Target customers at risk of churn:** Use customer purchase history to identify at-risk and high-value customers, then run targeted win-back campaigns to encourage them to return.

## Technical Details
- **Database:** PostgreSQL
- **Analysis Tools:** PostgreSQL, DBeaver, and pgAdmin
- **Visualizations:** Google Gemini