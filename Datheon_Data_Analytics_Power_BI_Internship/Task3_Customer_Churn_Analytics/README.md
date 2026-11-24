# Task 3: Customer cohort and churn analytics

## Objective

Find out which telecom customers leave, how long they stay, and which factors are linked to churn, using the IBM Telco Customer Churn dataset. The work ends with evidence-based retention recommendations.

## What is in this folder

| Path | Contents |
|---|---|
| `powerbi/` | The two-page Power BI dashboard (`Telco_Churn_Dashboard.pbix`) |
| `python/` | Jupyter notebook with the statistical tests, and its requirements |
| `data/` | `telco_customer_churn.csv` (7,043 customers, 21 columns) |
| `report/` | Written analysis report with methodology, results, recommendations and conclusions |


## Method

1. **Cleaning (Power Query).** All 7,043 customer IDs are unique. Eleven blank `TotalCharges` values belong to customers with 0 months of tenure who had not been billed yet, so they were set to 0 and the customers kept.
2. **New fields.** Tenure cohorts (0-12, 13-24, 25-48, 49-72 months) and monthly charge segments (Low under $35, Medium $35 to under $70, High $70 and above).
3. **DAX measures.** Total Customers, Churned Customers, Retained Customers, Churn Rate, Retention Rate, Average Monthly Charges, Monthly Revenue at Risk and Average Tenure. All respond to the slicers.
4. **Dashboard.** Page 1 shows the churn overview. Page 2 shows the cohort retention matrix and churn drivers. Slicers for contract, payment method and internet service are synced across pages.
5. **Statistics (Python).** Chi-square tests with Cramér's V, Mann-Whitney U tests, and a logistic regression to see what still matters when other factors are held constant.

## Main results

- **Overall:** 1,869 of 7,043 customers churned, a churn rate of 26.54%, which represents $139,131 in monthly revenue.
- **Contract:** month-to-month customers churn at 42.71%, against 11.27% on one-year and 2.83% on two-year contracts.
- **Tenure:** churn falls from 47.44% in the first year to 9.51% for customers with 49 to 72 months. 55.5% of all churners left in their first year.
- **Payment method:** electronic check users churn at 45.29%, against 15% to 19% for other methods.
- **High-risk segment:** fiber optic customers without tech support churn at 49.37%, against 22.63% with it. They are 31.7% of customers but 58.9% of all churners.
- **Statistical tests:** every factor tested is significantly linked to churn (all p-values below 0.001). After adjusting for other factors, contract type, fiber optic service, missing tech support and electronic check stay linked to churn.

## Retention recommendations

1. Move month-to-month customers onto longer contracts.
2. Put more effort into the first year of the customer relationship.
3. Offer tech support to fiber optic customers, starting with a pilot.
4. Encourage customers to move off electronic check.
5. Look into fiber optic service quality and value.
6. Build an early-warning list to contact the highest-risk customers first.

The full evidence behind each one is in the report.

## Limitations

The dataset is a one-time snapshot with no signup dates or monthly history. The cohort retention matrix is therefore tenure-based and is not a true month-by-month cohort curve. The analysis also shows association, not cause: the data has nothing on service quality, outages, satisfaction or competitor offers, so the recommendations should be tested with small pilots first.


## Dataset

IBM Telco Customer Churn, a public sample dataset.
