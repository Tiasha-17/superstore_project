# Superstore Sales and Profitability Analysis

## Project Overview
This project analyzes the `Sample - Superstore` dataset to identify where revenue is growing, where profit is leaking, and what business actions can improve margin.

As a first data science portfolio project, the focus is on translating analysis into clear, decision-ready insights for business stakeholders.

## Business Problem
Even when sales grow, companies can still lose profit due to discounting, product mix, and geographic performance differences.

This analysis answers:
- Which segments drive profit vs. just revenue?
- How do discounts affect profitability?
- Where are the biggest loss pockets (category, state, city)?
- How concentrated is profit across customers and orders?

## Dataset
- Source file: `Sample - Superstore.csv`
- Rows: `9,994`
- Columns: `21`
- Time period: `2014-2017`
- Unique orders: `5,009`
- Unique customers: `793`

## Tools and Skills Used
- Python
- Pandas
- Exploratory Data Analysis (EDA)
- Business KPI analysis
- Grouped aggregation and profitability segmentation

## Methodology
1. Loaded and validated data (used `latin1` encoding due to UTF-8 decode error).
2. Parsed date fields and created shipping lead time (`Ship Days`).
3. Computed core KPIs: total sales, total profit, margin.
4. Performed segment-level analysis by:
   - Category and sub-category
   - Region, state, and city
   - Customer segment and customer profitability
5. Analyzed discount impact using discount bands and threshold checks.
6. Measured concentration with:
   - Loss-making order share
   - 80/20-style customer contribution analysis

## Key KPIs
- Total Sales: `$2,297,200.86`
- Total Profit: `$286,397.02`
- Overall Profit Margin: `12.47%`
- Sales Growth (2014 to 2017): `+51.41%`
- Profit Growth (2014 to 2017): `+88.60%`

## Top 5 Business Insights
1. **Sales grew strongly, but margin softened in the latest year.**  
   Sales increased from `$484K` (2014) to `$733K` (2017), while margin peaked in 2016 (`13.43%`) and dipped to `12.74%` in 2017, signaling pressure on profitability.

2. **High discounting is the largest profit leakage driver.**  
   Orders with discount `>= 30%` account for only `15.79%` of sales but contribute `-$135,376.06` profit (`-37.32%` margin for that slice).

3. **Furniture generates revenue but underperforms on profit.**  
   Furniture contributes ~`32%` of sales but only `$18,451` profit (`2.49%` margin), far below Technology (`17.40%`) and Office Supplies (`17.04%`).

4. **Losses are concentrated in specific geographies.**  
   Largest state-level losses come from Texas (`-$25,729`), Ohio (`-$16,971`), and Pennsylvania (`-$15,560`), while California and New York are major profit engines.

5. **Profit is concentrated in a minority of customers, and many orders are unprofitable.**  
   About `20.4%` of orders are loss-making. Just `153` customers (out of `793`) generate `80%` of total profit, suggesting clear potential for account-level strategy.

## Business Recommendations
- Set discount guardrails by category and geography, especially for high-discount transactions.
- Reprice or rebundle low-margin Furniture sub-categories (especially Tables and Bookcases).
- Build a state-level turnaround plan for major loss regions before scaling promotions.
- Introduce customer-tier pricing and retention strategy to protect high-profit accounts.
- Track order-level margin in operations dashboards to reduce loss-making transactions.

## Suggested Visuals for Portfolio
- Sales and profit trend by year
- Profit margin by category and sub-category
- Discount band vs. profit/margin chart
- State-level profit map or bar chart
- Cumulative customer profit (Pareto curve)

## Project Structure
```text
superstore_project/
|- Sample - Superstore.csv
|- analysis.ipynb
|- README.md
```

## Reproducibility
1. Open `analysis.ipynb`.
2. Ensure Python and pandas are installed.
3. Run notebook cells from top to bottom.
4. Verify that key metrics match the values in this README.

## Interview Pitch (Short)
I analyzed 9,994 retail transactions to find why profit was lagging behind sales growth.  
The biggest issue was discount strategy: high-discount orders were a relatively small share of sales but created large losses. I also found product and state-level loss pockets and showed how targeted pricing and geography-specific actions can improve margin without depending only on revenue growth.
