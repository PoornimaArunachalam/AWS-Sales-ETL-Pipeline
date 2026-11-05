-- Create database
CREATE DATABASE IF NOT EXISTS sales_warehouse;

-- View product dimension
SELECT * FROM sales_warehouse.dim_product;

-- View sales fact
SELECT * FROM sales_warehouse.fact_sales;

-- Check zero-dollar sales
SELECT *
FROM sales_warehouse.fact_sales
WHERE sales_amount <= 0;

-- Final aggregated sales report
SELECT
    p.product_id,
    p.product_name,
    p.category,
    SUM(f.quantity) AS total_quantity,
    SUM(f.sales_amount) AS total_sales
FROM sales_warehouse.fact_sales f
JOIN sales_warehouse.dim_product p
ON f.product_id = p.product_id
GROUP BY
    p.product_id,
    p.product_name,
    p.category
ORDER BY total_sales DESC;
