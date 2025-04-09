# Subqueries and Nested SELECTs

**Subqueries** (also known as nested queries) allow you to embed one SQL query inside another. This makes it possible to break down complex problems into manageable parts — a technique especially useful when working with layered data in ERP systems.

---

## What is a Subquery?

A subquery is a query nested inside a `SELECT`, `FROM`, or `WHERE` clause. It helps retrieve data that will then be used by the main (outer) query.

Subqueries can be:

- **Inline** (also called non-correlated)
- **Correlated** (dependent on the outer query)

---

## Inline Subquery

Executes independently and passes its results to the outer query.

```sql
SELECT product_name
FROM products
WHERE product_id IN (
  SELECT product_id
  FROM sales
  WHERE sale_date = CURDATE()
);
```

📦 *Used to find all products sold today based on the sales table.*

---

## Correlated Subquery

Refers to columns from the outer query and runs once for each row evaluated by the outer query.

```sql
SELECT employee_name
FROM employees e
WHERE salary > (
  SELECT AVG(salary)
  FROM employees
  WHERE department_id = e.department_id
);
```

💼 *Used to find employees earning above the average salary in their department — helpful for HR analytics.*

---

## Use Cases in ERP

- 🛒 **Identify products never sold:**
  ```sql
  SELECT product_name
  FROM products
  WHERE product_id NOT IN (
    SELECT DISTINCT product_id
    FROM sales
  );
  ```

- 🧍 **Find inactive customers:**
  ```sql
  SELECT customer_id, customer_name
  FROM customers
  WHERE customer_id NOT IN (
    SELECT DISTINCT customer_id
    FROM orders
  );
  ```

- 🌍 **Select top-selling product by region:**
  (Typically done with a correlated subquery or a `RANK()` function in advanced SQL.)

---

## Best Practices

- ✅ Start by writing and testing the subquery independently.
- 🧪 Use `EXISTS`, `IN`, or `NOT IN` carefully with large datasets for performance.
- 💡 Replace subqueries with JOINs where appropriate — especially for optimization.
- 📊 Avoid nesting too deeply — it can reduce readability and increase processing time.

---

## Summary

Subqueries are incredibly versatile for building dynamic filters and deriving comparative logic in a single SQL statement. When working with complex ERP systems, subqueries can help you uncover hidden insights, identify edge cases, and build advanced reports.

> 🧠 **Tip:** Use subqueries when a value in your main query depends on a dynamic result set derived from other tables.