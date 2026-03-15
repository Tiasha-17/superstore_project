# Superstore Sales and Profitability Analysis

This is my first end-to-end data science portfolio project.  
I used the Superstore dataset to move beyond basic EDA and answer business questions on sales, profit, discounts, and customer concentration.

## Project Objective
The main goal of this project is to identify where the business is growing, where profit is leaking, and what practical actions can improve margins.

## Business Questions
1. Sales Performance
- Which region generates the highest sales revenue?
- Which product categories contribute the most to total sales?
- How does sales distribution vary across regions and categories?

2. Profitability Analysis
- Which product categories generate the highest profit?
- Are there categories with high sales but low profit?
- Which regions are most profitable for the business?

3. Discount Impact
- What is the relationship between discount levels and profit?
- At what discount levels does profit start to decline?
- Are certain product categories more sensitive to discounts?

4. Customer Insights
- Who are the top customers by total sales?
- Do a small number of customers account for a large share of revenue?

## Dataset
- File: `Sample - Superstore.csv`
- Total rows: `9,994`
- Total columns: `21`
- Date range: `2014-2017`
- Unique orders: `5,009`
- Unique customers: `793`
- Encoding used to load file: `latin1`

## Tech Stack
- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn

## Repository Structure
```text
superstore_project/
|- Sample - Superstore.csv
|- analysis.ipynb
|- README.md
|- PRESENTATION_SCRIPT.md
|- .gitignore
```

## Analysis Workflow
1. Data loading and validation.
2. Date conversion and feature engineering (`Ship Days`, yearly and period features).
3. KPI baseline calculation (sales, profit, margin, growth).
4. Segmentation analysis by region, category, sub-category, state, city, and customer segment.
5. Discount band analysis and threshold checks.
6. Root-cause analysis for loss pockets (`State x Sub-Category`).
7. Customer concentration and order-level profitability analysis.
8. Advanced extensions:
- Monthly and quarterly seasonality analysis.
- Discount-cap simulation (20% and 30% caps).
- Order-level profit/loss classification model.

## Core KPIs
- Total Sales: `$2,297,200.86`
- Total Profit: `$286,397.02`
- Overall Profit Margin: `12.47%`
- Sales Growth (2014 to 2017): `+51.41%`
- Profit Growth (2014 to 2017): `+88.60%`

### Yearly Trend
| Year | Sales | Profit | Margin |
|---|---:|---:|---:|
| 2014 | $484,247.50 | $49,543.97 | 10.23% |
| 2015 | $470,532.51 | $61,618.60 | 13.10% |
| 2016 | $609,205.60 | $81,795.17 | 13.43% |
| 2017 | $733,215.26 | $93,439.27 | 12.74% |

## Answers to Business Questions

### 1) Sales Performance
- Highest sales region: `West` with `$725,457.82` (`31.6%` of total sales).
- Sales by category:
- `Technology`: `$836,154.03` (`36.4%`)
- `Furniture`: `$741,999.80` (`32.3%`)
- `Office Supplies`: `$719,047.03` (`31.3%`)
- Regional distribution is fairly balanced, with West and East leading.

### 2) Profitability Analysis
- Most profitable category: `Technology` (`$145,454.95`).
- Next: `Office Supplies` (`$122,490.80`).
- High-sales but low-profit category: `Furniture`.
- Furniture profit margin is only `2.49%`, much lower than:
- Technology margin: `17.40%`
- Office Supplies margin: `17.04%`
- Most profitable region: `West` (`$108,418.45`), then `East` (`$91,522.78`).

### 3) Discount Impact
- Discount and profit are negatively correlated: `-0.219`.
- Profit margin turns negative starting from the `30-40%` discount band.
- Discount sensitivity by category (correlation of discount vs profit):
- `Furniture`: `-0.484` (most sensitive)
- `Technology`: `-0.269`
- `Office Supplies`: `-0.209`
- High-discount transactions (`>= 30%`) are only `15.79%` of sales but contribute `-$135,376.06` profit.

### 4) Customer Insights
- Top 10 customers by sales include:
- Sean Miller (`$25,043.05`)
- Tamara Chand (`$19,052.22`)
- Raymond Buch (`$15,117.34`)
- Customer concentration by revenue:
- 43 customers drive 20% of sales.
- 170 customers drive 50% of sales.
- 396 customers drive 80% of sales.
- Interpretation: revenue is not extremely concentrated in a very small set of customers.

## Advanced Analysis

### Seasonality Analysis
- Highest sales month: `Nov 2017` with `$118,447.82`.
- Highest profit month: `Dec 2016` with `$17,885.31`.
- Highest sales quarter: `2017 Q4` with `$280,054.07`.
- Highest profit quarter: `2016 Q4` with `$38,139.86`.
- Lowest monthly margin in the period: `Jan 2015` (`-18.05%`).

### Discount Cap Simulation
I simulated discount caps using the notebook assumption:
`Profit_Sim = Profit + (Discount - Discount_Capped) * Sales`

- If capped at `30%`:
- Simulated profit: `$337,658.52`
- Uplift: `+$51,261.50` (`+17.90%`)

- If capped at `20%`:
- Simulated profit: `$373,935.54`
- Uplift: `+$87,538.52` (`+30.57%`)

### Root-Cause Matrix (Loss Pockets)
Top loss pockets from `State x Sub-Category` include:
- Texas x Binders: `-$14,705.07`
- Ohio x Machines: `-$11,770.94`
- Illinois x Binders: `-$7,204.32`
- Texas x Appliances: `-$6,147.22`

### Predictive Modeling (Order-Level Profit/Loss)
I built a Random Forest classifier on order-level features to predict whether an order is profitable.

- Model: `RandomForestClassifier(n_estimators=100, random_state=42)`
- Test accuracy: `0.90`
- Confusion matrix:
- True negatives: `150`
- False positives: `55`
- False negatives: `45`
- True positives: `752`
- Most important feature: `Discount` (`0.584` importance)

## Key Findings Summary
- Sales grew strongly, but margin softened in the latest year.
- High discounts are the largest source of profit leakage.
- Furniture drives revenue but underperforms on profit.
- Losses are concentrated in specific states and sub-categories.
- Around `20.4%` of orders are loss-making.
- `153` customers (19.3% of customers) generate `80%` of total profit.

## Business Recommendations
- Set category- and region-level discount guardrails.
- Reprice, bundle, or limit low-margin Furniture sub-categories.
- Create focused turnaround plans for top loss pockets.
- Monitor order-level margin in operational dashboards.
- Use customer-tier strategy for retention and pricing decisions.

## How to Run
1. Clone the repository.
2. Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```
3. Open the notebook:
```bash
jupyter notebook analysis.ipynb
```
4. Run all cells from top to bottom.

## What I Learned
- Business impact comes from combining EDA with clear recommendations.
- Discount policy can change profitability more than raw sales growth.
- Segment-level analysis is necessary because aggregate KPIs can hide loss pockets.
- Adding simulation and predictive modeling makes analysis more decision-ready.

## Next Improvements
- Add a dashboard version (Power BI or Tableau).
- Validate discount simulation with a stronger causal framework.
- Try gradient boosting and calibration for more robust order-level prediction.
