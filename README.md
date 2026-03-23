#📦 E-Commerce SQL Analysis Project
SQL project analyzing e-commerce data using MySQL Workbench
This project showcases my ability to import, clean, and analyze real-world e-commerce data using **MySQL Workbench**. I worked with three datasets containing customer orders, purchased items, and customer details — and used SQL to uncover business insights.

## 🗂️ Datasets Used

- `olist_orders_dataset.csv` → `orders` table  
- `olist_order_items_dataset.csv` → `order_items` table  
- `olist_customers_dataset.csv` → `customers` table

- ## 🧹 Data Cleaning & Import

- Used `LOAD DATA INFILE` to import CSVs into MySQL
- Handled blank datetime values using `NULLIF(@column, '')`
- Resolved data type mismatches and path restrictions
- Verified row counts to ensure full import:
  - Orders: 99,441 rows  
  - Order Items: 112,650 rows  
  - Customers: ~100,000 rows
 
  - ## 📊 Analytical Queries

### 1. Total Revenue
```sql
SELECT SUM(price + freight_value) AS total_revenue
FROM order_items;
Result: ₹15,843,553.24

### 2. Top 10 Cities by Customers
SELECT customer_city, COUNT(customer_id) AS total_customers
FROM customers
GROUP BY customer_city
ORDER BY total_customers DESC
LIMIT 10;

### 3. Top Products by Sales
SELECT product_id, SUM(price) AS product_sales
FROM order_items
GROUP BY product_id
ORDER BY product_sales DESC
LIMIT 10;

### 4. Monthly Order Trends
SELECT DATE_FORMAT(order_purchase_timestamp, '%Y-%m') AS month,
       COUNT(order_id) AS total_orders
FROM orders
GROUP BY month
ORDER BY month;

---

### ✅ 5. **Key Learnings**
```markdown
## 💡 Key Learnings

- Real-world data often contains blanks and errors — handling them is crucial
- SQL is powerful for both cleaning and analysis
- MySQL Workbench is a great tool for visualizing and debugging queries
- This project mirrors what data analysts do in retail and e-commerce

## 📌 Next Steps

- Build Power BI dashboards using these queries
- Share insights on LinkedIn and connect with fellow data professionals

## 📬 Connect with Me

Feel free to reach out or share feedback!  
🔗 [LinkedIn](https://www.linkedin.com/in/kirti-vegad/)
