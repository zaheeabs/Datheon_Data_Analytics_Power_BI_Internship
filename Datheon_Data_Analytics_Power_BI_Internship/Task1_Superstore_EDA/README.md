# Task 1: Superstore retail sales exploratory data analysis

## Objective

Explore the Superstore Retail Sales dataset, clean it, and find out business findings about sales, profit and where the business is gaining or losing money.

## What is in this folder

| Path | Contents |
|---|---|
| `notebook/` | Jupyter notebook with the data cleaning code, analysis and annotated findings |
| `data/` | The dataset (`superstore_sales.csv`) |

## Approach

1. **Load and inspect.** The CSV stacks the orders, people and returns sheets into one file, so the first job was to separate them and check each part.
2. **Clean.** Fix data types, handle missing and duplicate values, and standardise inconsistent entries.
3. **Explore.** Look at sales and profit by category, region, segment and time using pandas and seaborn.
4. **Report findings.** Each finding is annotated in the notebook with the number behind it.

## Key findings


1.The business is healthy and growing 
2.Sales are strongly seasonal
3.Furniture is hvaing a profit problem , not a sales problem
4.Discounts above 20% destroys profit
5.The Central region is the weak spot, and discounting explains it

The dataset must be in the `data/` folder.
