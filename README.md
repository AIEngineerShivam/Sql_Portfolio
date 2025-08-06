# --Q1. What is the total sales in the entire dataset?

SELECT SUM(weekly_sales) AS total_sales
FROM walmart_sales;

--Q2.What is the average weekly sales for all stores?

SELECT AVG(weekly_sales) AS Avg_sales
FROM walmart_sales;

--Q3.How many unique stores are in the data?

SELECT COUNT(DISTINCT(store)) AS Unique_store
FROM walmart_sales;

--Q4.Which store had the highest sales?

SELECT store, MAX(weekly_sales) AS highest_sales
FROM walmart_sales
GROUP BY store
ORDER BY highest_sales DESC;

--Q5.Which store had the lowest sales?

SELECT store, MIN(weekly_sales) AS Lowest_sales
FROM walmart_sales
GROUP BY store
ORDER BY lowest_sales ASC;

--Q6. What is the maximum fuel price recorded?

SELECT MAX(fuel_price) AS Maximum_fuel
FROM walmart_sales;

--Q7.What is the average unemployment rate?

select * from walmart_sales;
SELECT AVG(unemployment) AS Avg_umployment_rate
FROM walmart_sales;

--Q8.What is the average temperature across all weeks?

SELECT  AVG(temperature) AS Avg_tem
FROM walmart_sales;

--Q9.How many times was there a holiday week?

SELECT COUNT(*) AS Holiday_week_count
FROM walmart_sales
WHERE holiday_flag = 1 ;

--Q10.What is the total number of weeks recorded in the data?

SELECT COUNT(DISTINCT(date)) AS Total_week
FROM walmart_sales;

--Q11.What was the total sales in February 2010?

SELECT SUM(weekly_sales) AS Total_sales
FROM walmart_sales
WHERE EXTRACT(YEAR FROM date) = 2010
    AND EXTRACT(MONTH FROM date) = 2;

--Q12.What was the weekly sales trend in 2011?

SELECT date, SUM(weekly_sales) AS Total_weekly_sales
FROM walmart_sales
WHERE EXTRACT(YEAR FROM date) = 2011
GROUP BY date
ORDER BY date;

--Q13.What is the earliest and latest dates in the dataset?

SELECT MIN(date) AS earliest_date,
       MAX(date) AS latest_date
	   FROM walmart_sales;

--Q14.What is the total sales of Store 1?

SELECT SUM(weekly_sales) AS Total_sales
FROM walmart_sales
WHERE store = 1;

--Q15.What is the average weekly sales of Store 5?

SELECT AVG(weekly_sales) AS Avg_sales
FROM walmart_sales
WHERE store = 5;
