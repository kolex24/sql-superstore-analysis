# sql-superstore-analysis
## Project Overview 
This project analyze the **Superstore dataset** using SQL to uncover key business insight related to sales, profit and customer trend. the goal is derive data-driven recommendations to improve profitability and customer engagement.
## Problem Statement
Superstore businesses needs to optimize sales performance, Identify high-value customers, amd maximize profit margins. this analysis aims to answer:
- Which product categories and subcategories are the most profitable ?
- How do sales and profit vary across different region and customer segment ?
- Are there any seasonal trend affecting sales performance ?
- Identify tge average total sales per order
- How many order is received.
## Skills Demonstration
During the analysis process, a diverse set of skills was demonstrated, including descriptive analysis of the dataset, SQL-based summarization, data transformation techniques, and exploratory statistical analysis to uncover business insight
 ## Data Tansformation & Data Cleaning
 To ensure data reliability and data integrity of the dataset the following steps are taken
 - Data loading and inspection
 - Removing duplicate
 - Handling null values Null value is found in the profit column

``` 
SELECT Profit FROM Superstore WHERE Profit IS NUll```

```
UPDATE SUPERSTORE SET Profit = 28.7017933364272 WHERE Profit IS NULL; ```


The full project can be seen [Here](https://github.com/kolex24/sql-superstore-analysis/blob/main/SQLQuery_SUPERSTORE.sql)

## Analysis Summary
1. ```
 SELECT SUB_CATEGORY,Category, SUM(Profit) [Total Profit] FROM Superstore
 GROUP BY Sub_Category, Category
 ORDER BY SUM(Profit) DESC;```
Technolgy has the highest profit generated (55617.82) in the Product category while Copiers has the highest profit generated in product sub-category

