# Aggregate Functions and Grouping

Aggregate functions allow you to perform calculations on sets of rows and return summarized values. These functions are especially powerful in ERP reporting, enabling insights like total sales, inventory counts, or average revenue per customer.

---

## Common Aggregate Functions

- `COUNT(*)` – Returns the total number of rows
- `SUM(column)` – Calculates the total value of a column
- `AVG(column)` – Computes the average value of a column
- `MIN(column)` / `MAX(column)` – Finds the lowest or highest values in a column

🔍 *These are essential for dashboards, performance metrics, and management reporting in ERP systems.*

---

## GROUP BY – Segmenting Data for Aggregation

`GROUP BY` is used to group rows based on one or more columns before applying an aggregate function.

```sql
SELECT customer_city, COUNT(*) AS total_customers
FROM customers
GROUP BY customer_city;
```

📊 *Great for generating summaries like customers by city, orders per region, or revenue by department.*

---

## HAVING – Filtering Grouped Results

Unlike `WHERE`, which filters rows before grouping, `HAVING` filters after aggregation.

```sql
SELECT employee_id, COUNT(*) AS orders_handled
FROM orders
GROUP BY employee_id
HAVING COUNT(*) > 20;
```

🎯 *Useful when analyzing productivity or performance thresholds (e.g., employees with more than 20 orders).*

---

## ERP Use Cases for Aggregates

- 📈 **Sales Analysis:** 
  - Total and average sales per region or sales rep
- 🏆 **Product Performance:**
  - Top 5 best-selling or slow-moving items
- 🧾 **Invoice Tracking:**
  - Number of unpaid invoices per customer
- 📦 **Inventory Summary:**
  - Count of items below minimum stock level
- 👥 **HR Insights:**
  - Average leave days per department

---

## Best Practices

- Use **aliases** (`AS`) to label your output clearly.
- Always include **GROUP BY** fields in the `SELECT` clause.
- Combine with **JOINs** to enrich grouped data (e.g., joining orders and customers).
- Leverage **ORDER BY** to rank or sort aggregate results.

---

## Summary

Aggregate functions are at the heart of ERP analytics. Whether you're tracking performance, analyzing sales, or generating dashboards, mastering SQL aggregates will empower you to turn raw data into actionable insights.

> 🧠 **Tip:** When building business reports, always validate the logic of your GROUP BY and HAVING clauses to ensure accuracy in your results.