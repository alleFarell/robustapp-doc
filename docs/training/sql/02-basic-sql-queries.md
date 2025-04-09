# Basic SQL Queries

Structured Query Language (SQL) is the universal language for accessing and manipulating data in relational databases. Mastering SQL is essential for Technical Consultants working with ERP systems, as it enables you to retrieve, analyze, and act on critical business data efficiently.

## SELECT Statement

The `SELECT` statement is the cornerstone of SQL. It allows you to retrieve specific columns or entire rows from one or more tables.

```sql
SELECT customer_name, phone_number
FROM customers;
```

✅ *Use `SELECT` to fetch only the fields you need — this improves performance and readability.*

## Filtering with WHERE

The `WHERE` clause helps filter records based on specified conditions, allowing for more targeted queries.

```sql
SELECT * 
FROM orders
WHERE order_status = 'Pending';
```

🔎 *Ideal for pulling up current tasks, exceptions, or filtered business records (e.g., unpaid invoices).*

## Sorting Results with ORDER BY

Use `ORDER BY` to sort results by one or more columns. Add `ASC` (ascending) or `DESC` (descending) to control sort direction.

```sql
SELECT product_name, price
FROM products
ORDER BY price DESC;
```

📊 *Common use cases include viewing the most expensive items, latest transactions, or top-selling products.*

## Limiting Results with LIMIT

`LIMIT` is used to restrict the number of rows returned — useful for performance and previews.

```sql
SELECT * 
FROM inventory
LIMIT 5;
```

💡 *Use it when validating queries or previewing data without overloading the output.*

## Eliminating Duplicates with DISTINCT

`DISTINCT` returns unique values from a column, which is useful when summarizing or identifying patterns.

```sql
SELECT DISTINCT customer_city
FROM customers;
```

🌍 *This helps you understand geographic distribution or prevent duplicate reporting.*

## Practical ERP Scenarios

- 🔹 Show all invoices where the status is `Unpaid`
- 🔹 List all products that are currently out of stock
- 🔹 Retrieve the five most recent customer registrations
- 🔹 View a list of unique vendors supplying inventory items

---

## Summary

Basic SQL queries are powerful tools that give you direct access to the data underpinning ERP modules. By mastering commands like `SELECT`, `WHERE`, `ORDER BY`, and `LIMIT`, you can gain immediate insights, troubleshoot issues, and support data-driven decision-making.

> 🧠 **Tip:** Always validate your queries in a test environment before executing them on production systems.