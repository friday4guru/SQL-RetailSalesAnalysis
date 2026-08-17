# SQL-RetailSalesAnalysis
## SQL Queries
### Data Cleaning
### 1. Check for the columns that contains Nulls
```sql
SELECT *
FROM RetailSalesAnalysis
WHERE transactions_id IS NULL 
OR sale_date IS NULL
OR sale_time IS NULL
OR customer_id IS NULL
OR gender IS NULL
OR age IS NULL
OR category IS NULL
OR quantiy IS NULL
OR sale_time IS NULL
OR price_per_unit IS NULL
OR cogs IS NULL
OR total_sale IS NULL
````
### 2. Delete all the rows where there is any null values
```sql
DELETE FROM RetailSalesAnalysis
WHERE 
	transactions_id IS NULL 
	OR sale_date IS NULL
	OR sale_time IS NULL
	OR customer_id IS NULL
	OR gender IS NULL
	OR age IS NULL
	OR category IS NULL
	OR quantiy IS NULL
	OR sale_time IS NULL
	OR price_per_unit IS NULL
	OR cogs IS NULL
	OR total_sale IS NULL
```
## Data Exploration 
### 3. How many sales do we have 
```sql
SELECT
  COUNT(*) CountOfSale
FROM RetailSalesAnalysis
```
### 4. How many unique customers do we have 
```sql
SELECT
    COUNT(DISTINCT customer_id) CountOfCustomer
FROM RetailSalesAnalysis
```
### 5. How many unique Product category do we have 
```sql
SELECT
    COUNT(DISTINCT category) CountOfCustomer
FROM RetailSalesAnalysis
```
### 6. List the unique product category?
```sql
SELECT DISTINCT category Product_Category
FROM RetailSalesAnalysis
```
### 8. retrieve all columns for sales made on '2022-11-05'.
``` sql
SELECT*
FROM RetailSalesAnalysis
WHERE sale_date = '2022-11-05'
```
### 9. retrieve all transactions where the category is 'Clothing' and the quantity sold is at least 4 in the month of Nov-2022.
```sql
SELECT*
FROM RetailSalesAnalysis
WHERE category = 'Clothing'
AND	  quantiy >=4
AND  FORMAT(sale_date, 'yyyy-MM') = '2022-12'
```

-- 10. Write a SQL query to calculate the total sales (total_sale) for each category.
```sql
SELECT
category,
SUM(total_sale) TotalSalesByCategory
FROM RetailSalesAnalysis
GROUP BY category
```
