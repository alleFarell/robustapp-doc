# Working with Multiple Tables

In real-world ERP systems, data is rarely confined to a single table. Information is normalized and distributed across multiple related tables for efficiency and integrity. To analyze or report on this data, you need to **join** these tables together.

## Understanding JOINs in SQL

A **JOIN** allows you to combine rows from two or more tables based on a related column between them — usually a foreign key relationship.

### INNER JOIN

Returns only the records that have matching values in both tables.

```sql
SELECT orders.order_id, customers.customer_name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.customer_id;
```

🧾 *Useful for retrieving order details along with customer information.*

---

### LEFT JOIN (or LEFT OUTER JOIN)

Returns all records from the left table, and the matched records from the right table. If there's no match, NULLs are returned for the right side.

```sql
SELECT products.product_name, inventory.stock_level
FROM products
LEFT JOIN inventory ON products.product_id = inventory.product_id;
```

📦 *Helpful when identifying products that exist but are not yet stocked.*

---

### RIGHT JOIN (or RIGHT OUTER JOIN)

Returns all records from the right table, and the matched records from the left. If there's no match, NULLs are returned for the left side.

```sql
SELECT inventory.stock_level, products.product_name
FROM inventory
RIGHT JOIN products ON inventory.product_id = products.product_id;
```

🔁 *Less common in ERP but useful when prioritizing a secondary table like stock.*

---

### FULL OUTER JOIN

Returns all records when there's a match in **either** table. If no match, NULLs are filled in accordingly.

> 🔄 Not all database engines (like MySQL) support FULL OUTER JOIN directly — alternatives include using `UNION`.

```sql
SELECT customer_name, order_id
FROM customers
FULL OUTER JOIN orders ON customers.customer_id = orders.customer_id;
```

---

## ERP Use Cases for JOINs

- 🧾 Combine customer and order details for invoicing
- 📦 List all products including those not currently in inventory
- 💳 Match payments with invoices for aging reports
- 🔗 Link employee records to their departmental info

---

## Best Practices for Multi-Table Queries

- Use **aliases** (e.g., `c` for `customers`) to improve query readability.
- Always define **join conditions** clearly to avoid Cartesian products.
- Limit result sets with `WHERE` or `LIMIT` to test before running large joins.
- Use **INNER JOIN** when you only need records with a clear relationship.
- Use **LEFT JOIN** when the presence of the left-side data is mandatory.

---

## Summary

Joining tables is one of the most powerful techniques in SQL. In the context of ERP, it enables you to correlate information across business modules — such as linking customers, orders, invoices, and payments — to build meaningful reports and perform critical analysis.

> 🧠 **Tip:** Understand entity relationships in your ERP schema. This knowledge will guide you in choosing the right type of JOIN for each scenario.