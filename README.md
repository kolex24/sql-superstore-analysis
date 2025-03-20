# sql-superstore-analysis
## Project Overview 
This project analyze the **Superstore dataset** using SQL to uncover key business insight related to sales, profit and customer trend. the goal is derive data-driven recommendations to improve profitability and customer engagement.
## Problem Statement
Superstore businesses needs to optimize sales performance, Identify high-value customers, amd maximize profit margins. this analysis aims to answer:
- Which product categories and subcategories are the most profitable ?
- How do sales and profit vary across different region and customer segment ?
- Are there any seasonal trend affecting sales performance ?
- What is the average total sales per order?
- How many order is received.
## Skills Demonstration
During the analysis process, a diverse set of skills was demonstrated, including descriptive analysis of the dataset, SQL-based summarization, data transformation techniques, and exploratory statistical analysis to uncover business insight
 ## Data Tansformation & Data Cleaning
 To ensure data reliability and data integrity of the dataset the following steps are taken
 - Data loading and inspection
 - Removing duplicate
 - Handling null values Null value is found in the profit column

``` 
SELECT Profit FROM Superstore WHERE Profit IS NUll
```

```
UPDATE SUPERSTORE SET Profit = 28.7017933364272 WHERE Profit IS NULL;
 ```


The full project can be seen [Here](https://github.com/kolex24/sql-superstore-analysis/blob/main/SQLQuery_SUPERSTORE.sql)

## Analysis Summary
```
 SELECT SUB_CATEGORY,Category, SUM(Profit) [Total Profit] FROM Superstore
 GROUP BY Sub_Category, Category
 ORDER BY SUM(Profit) DESC;
 ```

Technolgy has the highest profit generated in the Product category while Copiers has the highest profit generated in product sub-category

```
 SELECT REGION, segment, ROUND(SUM(SALES), 2) [TOTAL REVENUE ] FROM Superstore
 GROUP BY Region, Segment
 ORDER BY SUM(SALES) DESC;
```

Higher Sales are generated in the west region, also the consumer generated the highest sales in the customer segment while lower salest are generated in the south region and homw office customer segment.

```
SELECT REGION, segment, ROUND(SUM(PROFIT), 2) [TOTAL PROFIT] FROM Superstore
 GROUP BY Region, segment
 ORDER BY SUM(PROFIT) DESC;
```

Higher profit are generated in the west region, also the consumer generated the highest profit in the customer segment while lower salest are generated in the south region and homw office customer segment.

```
SELECT YEAR(Order_Date) [Year], DATEPART(QUARTER, Order_Date) [Quarter], SUM(SALES) [Total Sales] FROM Superstore
GROUP BY YEAR(Order_Date), DATEPART(QUARTER, Order_Date)
ORDER BY YEAR, Quarter;
```

There is a consistent trend in the sales across all the years whetre sales tend to increase in 4th quarter of the year across all year while there is a lower sales in 1st quarter of the year across all years

```
 SELECT ROUND(AVG(TOTAL_ORDER_SALES), 2) [AVERAGE SALES] FROM 
 (SELECT Order_ID, SUM(SALES) [TOTAL_ORDER_SALES] FROM SUPERSTORE 
 GROUP BY Order_ID) AS ORDER_SALES;
```

the  average sales per order (458.61)

```
SELECT COUNT(Order_ID) Orders FROM SUPERSTORE;
```

Total order superstore receieved (9994)
