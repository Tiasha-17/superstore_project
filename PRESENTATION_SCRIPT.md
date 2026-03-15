# Superstore Project Presentation Script (1 Page)

## Title
**From Sales Growth to Profit Growth: A Superstore Profitability Analysis**

## 1) Business Context (10-15 sec)
I analyzed the Superstore retail dataset to answer one practical question:  
why can a business grow sales but still struggle with profitability?

The dataset has 9,994 transactions across 2014 to 2017, with 5,009 orders and 793 customers.

## 2) Objective (10 sec)
My objective was to identify the biggest profit drivers and profit leakages across product mix, discounting, geography, and customer behavior, then convert findings into business actions.

## 3) Method (20-25 sec)
I used Python and pandas for exploratory and business KPI analysis.
I started with core KPIs, then segmented profitability by category, sub-category, region/state/city, and customer groups.
I also ran discount-band analysis and order-level profitability checks to find where losses were concentrated.

## 4) Key Findings (45-60 sec)
The business generated $2.30M in sales and $286K profit, with a 12.47% overall margin.  
Sales grew 51.41% from 2014 to 2017, and profit grew 88.60%, but margin softened in the final year.

The strongest insight was discount risk:
- Orders with discounts of 30% or more were only 15.79% of sales
- But they contributed about -$135K profit

I also found product-mix imbalance:
- Furniture drove high revenue but only 2.49% margin
- Technology and Office Supplies were much healthier at ~17% margin
- Tables and Bookcases were key loss-making sub-categories

Losses were geographically concentrated, especially in Texas, Ohio, and Pennsylvania, while California and New York were major profit contributors.
At the customer/order level, about 20.4% of orders were loss-making, and just 153 of 793 customers generated 80% of total profit.

## 5) Recommendations (20-25 sec)
Based on this, I recommended:
- Discount guardrails by category and geography
- Repricing/rebundling for low-margin Furniture sub-categories
- State-level turnaround plans for recurring loss regions
- Customer-tier strategy to protect high-profit accounts
- Order-level margin monitoring in daily operations

## 6) Closing (10 sec)
This project shows how I move from EDA to decision-ready insights.
The value is not only explaining what happened, but showing what the business should do next to improve profitability.

---

## Optional 30-Second Version
I analyzed 9,994 retail transactions to understand why profit was under pressure despite sales growth.  
Using Python and pandas, I found that high discounts were the biggest leakage point: discounts >=30% were only 15.79% of sales but drove about -$135K profit. I also identified low-margin product and geography pockets, especially in Furniture and a few states. My recommendations focused on discount guardrails, product repricing, and targeted regional actions to improve margin without relying only on revenue growth.
