# Aggregate-Function2
use sample ;
CREATE TABLE sales (
    id INT AUTO_INCREMENT PRIMARY KEY,
    product_name VARCHAR(50),
    category VARCHAR(30),
    price DECIMAL(10,2),
    quantity_sold INT,
    sale_date DATE
);

INSERT INTO sales (product_name, category, price, quantity_sold, sale_date) VALUES
('Laptop', 'Electronics', 55000.00, 10, '2024-01-10'),
('Smartphone', 'Electronics', 25000.00, 20, '2024-01-15'),
('Tablet', 'Electronics', 15000.00, 15, '2024-01-20'),
('Headphones', 'Accessories', 2000.00, 30, '2024-02-05'),
('Smartwatch', 'Accessories', 5000.00, 25, '2024-02-10'),
('Mouse', 'Accessories', 800.00, 40, '2024-02-15'),
('Keyboard', 'Accessories', 1500.00, 35, '2024-02-20'),
('Monitor', 'Electronics', 12000.00, 18, '2024-02-25'),
('Printer', 'Electronics', 8000.00, 12, '2024-03-01'),
('Speakers', 'Accessories', 3000.00, 28, '2024-03-05'),
('Camera', 'Electronics', 30000.00, 8, '2024-03-10'),
('Game Console', 'Electronics', 40000.00, 7, '2024-03-15'),
('External Hard Drive', 'Accessories', 6000.00, 20, '2024-03-20'),
('Flash Drive', 'Accessories', 1200.00, 50, '2024-03-25'),
('Tripod', 'Accessories', 3500.00, 22, '2024-04-01'),
('Microphone', 'Accessories', 4500.00, 15, '2024-04-05'),
('Router', 'Electronics', 2500.00, 27, '2024-04-10'),
('Projector', 'Electronics', 55000.00, 5, '2024-04-15'),
('Fitness Band', 'Accessories', 3800.00, 34, '2024-04-20'),
('Power Bank', 'Accessories', 2200.00, 42, '2024-04-25'),
('Desktop', 'Electronics', 65000.00, 6, '2024-05-01'),
('VR Headset', 'Electronics', 45000.00, 4, '2024-05-05'),
('Smart TV', 'Electronics', 70000.00, 3, '2024-05-10'),
('Bluetooth Speaker', 'Accessories', 3500.00, 29, '2024-05-15'),
('Car Charger', 'Accessories', 1500.00, 37, '2024-05-20'),
('E-Book Reader', 'Electronics', 12000.00, 9, '2024-05-25'),
('Wireless Earbuds', 'Accessories', 6500.00, 26, '2024-06-01'),
('Drone', 'Electronics', 85000.00, 2, '2024-06-05'),
('Gimbal', 'Accessories', 7500.00, 16, '2024-06-10'),
('Graphics Tablet', 'Electronics', 30000.00, 5, '2024-06-15'),
('Gaming Chair', 'Accessories', 18000.00, 11, '2024-06-20'),
('Laptop Stand', 'Accessories', 2500.00, 33, '2024-06-25'),
('Cooling Pad', 'Accessories', 1700.00, 31, '2024-07-01'),
('Wireless Mouse', 'Accessories', 1300.00, 39, '2024-07-05'),
('Gaming Mouse', 'Accessories', 4500.00, 18, '2024-07-10'),
('Gaming Keyboard', 'Accessories', 7500.00, 13, '2024-07-15'),
('VR Controllers', 'Electronics', 9000.00, 7, '2024-07-20'),
('Soundbar', 'Accessories', 20000.00, 9, '2024-07-25'),
('Wired Earphones', 'Accessories', 900.00, 44, '2024-08-01'),
('Smart Lock', 'Electronics', 15000.00, 6, '2024-08-05'),
('Digital Pen', 'Accessories', 2800.00, 23, '2024-08-10'),
('Tablet Stand', 'Accessories', 1900.00, 38, '2024-08-15'),
('Home Assistant', 'Electronics', 7000.00, 10, '2024-08-20');

-- 50 MySQL Questions --

--- 1. Retrieve all records from the sales table.
select * from sales;
--- 2. Get the total number of records in the sales table.
select count(*) as total_number_of_record from sales;
--- 3. Find the total revenue generated from sales.
select sum(price*quantity_sold) as total_revenue from sales;
--- 4. Retrieve the most expensive product.
select max(price) as most_expensive from sales;
--- 5. Find the cheapest product.
select min(price) as cheapest from sales;
--- 6. Retrieve products sold in the month of March.
select product_name ,sale_date from sales where sale_date between '2024-03-01' and '2024-03-31';

--- 7. Find the average price of all products.
select * from sales;
select avg(price) from sales;
--- 8. Count the number of sales transactions per category.
select category,count(*) as number_of_transactions from sales group by category ;
--- 9. Retrieve the product with the highest quantity sold.
select max(quantity_sold) from sales;
--- 10. Find the product with the lowest quantity sold.
select min(quantity_sold) from sales;
--- 11. Retrieve sales details for Electronics category.
select * from sales;
select * from sales where category='Electronics';
--- 12. Find total sales revenue for Accessories category.
select sum(price*quantity_sold) as total_revenue from sales where category='Accessories';
--- 13. Retrieve products where quantity sold is greater than 20.
select product_name,quantity_sold from sales where quantity_sold > 20;
--- 14. List sales data ordered by sale_date in descending order.
select * from sales order by sale_date desc;
--- 15. Retrieve the top 5 most expensive products.

select product_name ,price from sales order by price desc limit 5;
--- 16. Find the sum of quantity_sold for all products.
select sum(quantity_sold) from sales;
--- 17. Retrieve distinct product categories.
select distinct category from sales;
--- 18. Count how many times each product was sold.
select product_name,count(*) as product_sold from sales group by product_name;
--- 19. Retrieve the latest 10 sales transactions.
select * from sales order by sale_date desc limit 10;
--- 20. Find the most recent sale date.
select max(sale_date) from sales;
--- 21. Find the total revenue generated in February.
select sum(price*quantity_sold) as total_revenue from sales where month(sale_date)=2;

--- 22. Retrieve sales where price is between 5000 and 20000.
select * from sales where price between 5000 and 20000;
--- 23. Find the average quantity sold per transaction.
select avg(quantity_sold) from sales;
--- 24. List products whose name starts with 'S'.
select product_name from sales where product_name like 'S%';
--- 25. Retrieve sales where quantity_sold is even.
select * from sales;
select * from sales where quantity_sold%2=0;
--- 26. Retrieve the first 10 sales transactions.
select * from sales limit 10;
--- 27. Find the maximum price in the Accessories category.
select category,max(price) from sales where category='Accessories';
--- 28. Retrieve products that were sold exactly 30 times.
select product_name from sales where quantity_sold=30;
--- 29. Count the number of sales transactions per month.
select month(sale_date),count(*) as no_of_sale_transaction from sales group by month(sale_date);
--- 30. Retrieve products sold before April 2024.
select * from sales;
select Product_name,sale_date from sales where sale_date between '2024-01-01' and '2024-03-31';
select * from sales where sale_date < '2024-04-01';
--- 31. Retrieve products with names ending in 'e'.
select product_name from sales where product_name like '%e';

--- 32. Find total sales revenue in the second quarter.
select sum(price*quantity_sold) as revenueQ2 from sales where month(sale_date) between 4 and 6;
--- 33. Retrieve the top 3 best-selling products.
select * from sales;
select product_name,sum(quantity_sold) as total_quantity from sales group by product_name order by total_quantity desc limit 3;
--- 34. List the first and last sale transaction.
(select * from sales order by sale_date asc limit 1)
union
(select * from sales order by sale_date desc limit 1);
--- 35. Find products priced above the average price.
select * from sales where price > (select avg(price) from sales );
--- 36. Retrieve sales data skipping the first 5 transactions.
select * from sales limit 43 offset 5;

--- 37. Find products where price is a multiple of 1000.
select product_name from sales where price % 1000=0;
--- 38. Retrieve products with 'Wireless' in their name.
select product_name from sales where product_name like '%Wireless%';
--- 39. Find the maximum quantity sold in Electronics.
select max(quantity_sold) from sales where category='Electronics';
--- 40. Retrieve sales for products sold in odd quantities.
select * from sales where quantity_sold%2 !=0;
--- 41. Retrieve sales transactions for July.
select * from sales where month(sale_date)= 07;
--- 42. Find total revenue from products sold after June.
select sum(price* quantity_sold) as total_revenue from sales where month(sale_date) >6; 
--- 43. Retrieve the most recent 15 transactions.
select * from sales order by sale_date desc limit 15;
--- 44. Find products whose price is a prime number.
select product_name,price from sales where price %1 and price%price=0; 
--- 45. Retrieve sales where price is greater than twice the quantity.
select * from sales where price > (2*quantity_sold); 
--- 46. Find products sold at least 10 times.
select * from sales where quantity_sold > 10;
--- 47. Retrieve sales transactions with price ending in '00'.
select * from sales where price like '%00';
--- 48. Find total sales per category ordered by revenue.
select category,sum(price*quantity_sold) as revenue from sales group by category order by revenue;
--- 49. Retrieve the second most expensive product.
select * from sales order by price desc limit 1 offset 1 ;
--- 50. List all transactions sorted by product name.
select * from sales order by product_name;
