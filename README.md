1.Total revenue
select * from  pizza_sales_excel_file

2.Total revenueAverage order value
select Sum(total_price) As Total_revenue from pizza_sales_excel_file

3.Average order value
select Sum(total_price)/count(DISTINCT order_id) As Average_order_value from pizza_sales_excel_file

4.total pizza sold
select Sum(quantity) As Total_pizza_sold from pizza_sales_excel_file

5.total orders
select count(distinct order_id) As Total_orders from pizza_sales_excel_file


6.Average pizza per order
SELECT CAST (CAST(SUM(quantity) As DECIMAL(10,2)) / cast(count(distinct order_id) AS decimal (10,2)) As decimal(10,2))
as Avg_pizzas_per_order from pizza_sales_excel_file

7.Daily Trend for total orders
select datename(DW, order_date) as order_day, count(distinct order_id) As Total_orders from pizza_sales_excel_file
GROUP  by datename (DW,order_date)
