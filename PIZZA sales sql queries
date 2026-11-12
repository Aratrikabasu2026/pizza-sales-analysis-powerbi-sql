CREATE TABLE pizza_sales (

pizza_id INTEGER PRIMARY KEY,
order_id	INTEGER NOT NULL,
pizza_name_id	VARCHAR(50),
quantity	INTEGER NOT NULL,
order_date	DATE NOT NULL,
order_time	TIME NOT NULL,
unit_price	NUMERIC(6,2) NOT NULL,
total_price	NUMERIC(8,2) NOT NULL,
pizza_size	VARCHAR(5) NOT NULL,
pizza_category	VARCHAR(20) NULL NULL,
pizza_ingredients	TEXT,
pizza_name VARCHAR(100) NOT NULL

);
--Q1
SELECT * FROM pizza_sales
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales

--Q2
SELECT SUM(total_price) / COUNT(DISTINCT order_id) 
AS avg_ordere_value FROM pizza_sales

--Q3
SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales

--Q4
SELECT COUNT(DISTINCT order_id) AS Total_orders FROM pizza_sales

--Q5
SELECT CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / CAST(COUNT(DISTINCT order_id) AS DECIMAL (10,2))
AS DECIMAL(10,2)) AS  avG_pizza_per_order 
from pizza_sales 

--Q6
select * from pizza_sales

SELECT TO_CHAR(order_date,'Day') as order_day, 
COUNT(DISTINCT order_id) as Total_orders 
FROM pizza_sales
GROUP BY TO_CHAR(order_date,'Day');

--Q7
SELECT TO_CHAR(order_date, 'Month') as Month_name,
COUNT(DISTINCT order_id) AS Total_orders
FROM pizza_sales
GROUP BY TO_CHAR(order_date, 'Month')
ORDER BY total_orders DESC

--Q8
SELECT pizza_category, 
SUM(total_price) as Total_Sales,
ROUND(SUM(total_price) * 100 / (SELECT SUM(total_price) 
FROM pizza_sales 
WHERE EXTRACT (MONTH FROM order_date) = 1),2) AS PCT
FROM pizza_sales
WHERE EXTRACT(MONTH FROM order_date)=1
GROUP BY pizza_category
ORDER BY pct DESC;

--Q9
SELECT pizza_size, 
SUM(total_price) as Total_Sales,
ROUND(SUM(total_price) * 100 / (SELECT SUM(total_price) 
FROM pizza_sales 
WHERE EXTRACT (MONTH FROM order_date) = 1),2) AS PCT
FROM pizza_sales
WHERE EXTRACT(MONTH FROM order_date)=1
GROUP BY pizza_size
ORDER BY pct DESC;

--Q10
SELECT pizza_name,
SUM(total_price) AS Total_revenue 
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue DESC
LIMIT 5

--Q11
SELECT pizza_name,
COUNT(DISTINCT order_id) AS Total_orders FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_orders DESC
LIMIT 5



