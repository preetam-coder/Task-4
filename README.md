🎯 Objective
The objective of this task is to use SQL aggregate functions and grouping techniques to summarize and analyze tabular data.
This task focuses on:
Applying aggregate functions on numeric columns
Categorizing data using GROUP BY
Filtering grouped results using HAVING
Combining tables using JOIN
Sorting results using ORDER BY
🛠 Tools Used
SQL Query Runner
🗂 Database Tables Used
This task uses three tables:
1️⃣ Customers
Stores customer information.
Column Name
Description
customer_id
Unique ID of customer
first_name
Customer first name
last_name
Customer last name
age
Customer age
country
Customer country
2️⃣ Orders
Stores order details placed by customers.
Column Name
Description
order_id
Unique order ID
item
Product name
amount
Order amount
customer_id
References Customers table
3️⃣ Shippings
Stores shipping status information.
Column Name
Description
shipping_id
Unique shipping ID
status
Shipping status (Pending/Delivered)
customer
Customer ID
📊 SQL Operations Performed
✅ 1. Aggregate Functions
The following aggregate functions were implemented:
SUM() → To calculate total sales
COUNT() → To count total orders and customers
AVG() → To calculate average order value
Example:
Sql
Copy code
SELECT SUM(amount) AS total_sales FROM Orders;
✅ 2. GROUP BY Clause
The GROUP BY clause was used to categorize data based on:
Customer-wise total spending
Number of orders per customer
Country-wise customer count
Shipping status summary
Example:
Sql
Copy code
SELECT customer_id, SUM(amount)
FROM Orders
GROUP BY customer_id;
✅ 3. HAVING Clause
The HAVING clause was used to filter grouped results.
Example:
Sql
Copy code
SELECT customer_id, SUM(amount)
FROM Orders
GROUP BY customer_id
HAVING SUM(amount) > 500;
This displays only customers who spent more than 500.
✅ 4. JOIN Operations
The JOIN operation was used to combine Customers and Orders tables for better analysis.
Example:
Sql
Copy code
SELECT C.first_name, C.last_name, SUM(O.amount)
FROM Customers C
JOIN Orders O
ON C.customer_id = O.customer_id
GROUP BY C.customer_id;
This shows total spending along with customer names.
✅ 5. ORDER BY Clause
The ORDER BY clause was used to sort summarized data in ascending or descending order.
Example:
Sql
Copy code
ORDER BY total_spent DESC;
📈 Analysis Performed
Using SQL queries, the following analysis was completed:
Total overall sales
Average order value
Customer-wise total spending
High-value customers
Country-wise sales summary
Shipping status distribution
🎓 Learning Outcome
After completing this task, I gained:
Practical understanding of SQL aggregate functions
Clear knowledge of GROUP BY and HAVING
Ability to summarize large datasets
Understanding of combining multiple tables using JOIN
Experience in real-world data analysis using SQL
