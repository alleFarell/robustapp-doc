# SQL Functions and Expressions

SQL offers a wide array of **built-in functions** and **conditional expressions** that help you manipulate, transform, and analyze data directly in your queries. These functions are essential for cleaning, formatting, and enriching data — tasks frequently encountered in ERP customization, reporting, and data preparation.

---

## String Functions

Used to transform and analyze text data.

```sql
SELECT UPPER(customer_name), LENGTH(customer_name)
FROM customers;
```

✉️ *Standardize case formatting (e.g., UPPER, LOWER) or measure field length for validations.*

---

## Common String Functions

| Function        | Description                                |
|----------------|--------------------------------------------|
| `UPPER(text)`  | Converts text to uppercase                 |
| `LOWER(text)`  | Converts text to lowercase                 |
| `LENGTH(text)` | Returns number of characters in a string   |
| `CONCAT()`     | Joins multiple strings into one            |
| `SUBSTRING()`  | Extracts a portion of a string             |

---

## Date Functions

Operate on date and time fields for calculation or formatting.

```sql
SELECT NOW(), DATE_ADD(order_date, INTERVAL 7 DAY)
FROM orders;
```

📆 *Common for calculating due dates, lead times, and delivery windows.*

---

## Common Date Functions

| Function              | Description                                    |
|-----------------------|------------------------------------------------|
| `NOW()`              | Returns the current date and time             |
| `CURDATE()`          | Returns the current date                      |
| `DATE_ADD(date, INTERVAL X)` | Adds interval to a date               |
| `DATEDIFF(date1, date2)` | Returns difference in days between dates  |
| `YEAR(date)` / `MONTH(date)` | Extracts year or month from a date   |

---

## Conditional Logic with CASE

The `CASE` statement lets you create conditional logic directly within your query — similar to `IF` statements in programming.

```sql
SELECT order_id,
       CASE 
         WHEN order_status = 'P' THEN 'Pending'
         WHEN order_status = 'C' THEN 'Completed'
         ELSE 'Other'
       END AS status_label
FROM orders;
```

⚙️ *Ideal for translating codes into human-readable labels or flagging statuses.*

---

## ERP Applications

- 📅 **Calculate days overdue** on invoices:
  ```sql
  SELECT invoice_id, DATEDIFF(NOW(), due_date) AS days_overdue
  FROM invoices
  WHERE payment_status = 'Unpaid';
  ```

- 🧮 **Derive fiscal periods or age** from birthdates or transaction dates
- 🧾 **Format tax codes or addresses** for reporting consistency
- 📦 **Label orders** by fulfillment status or aging categories

---

## Best Practices

- Use **function chaining** (e.g., `UPPER(TRIM(name))`) for compound transformations.
- Be mindful of **performance** when applying functions to indexed columns — they can disable index use.
- Apply **CASE** for classification or decision-making logic in dynamic reports.

---

## Summary

SQL functions and expressions are powerful tools that enhance the flexibility and intelligence of your queries. In ERP systems, they empower you to make raw data more meaningful, accurate, and aligned with business needs — all without extra processing on the application side.

> 🧠 **Tip:** Use functions strategically to minimize the need for post-processing in reporting tools like Power BI or Excel.