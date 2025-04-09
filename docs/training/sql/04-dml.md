# Data Manipulation Language (DML)

**Data Manipulation Language (DML)** includes the SQL commands that allow you to **insert**, **update**, and **delete** records in a relational database. These operations are essential for maintaining up-to-date and accurate information within ERP systems.

As a Technical Consultant, you’ll use DML to support real-time business operations such as managing inventory levels, updating pricing, and cleaning out deprecated records.

---

## INSERT INTO – Adding New Records

Used to insert new rows into a table.

```sql
INSERT INTO suppliers (name, city)
VALUES ('ABC Supplies', 'Jakarta');
```

✅ *Use this when onboarding new vendors, customers, or adding records to master data tables.*

---

## UPDATE – Modifying Existing Data

Used to change data in existing records. Always use a `WHERE` clause to avoid unintended bulk updates.

```sql
UPDATE products
SET price = 150000
WHERE product_id = 101;
```

🛠️ *Common for price adjustments, account updates, or correcting erroneous data.*

---

## DELETE – Removing Records

Deletes one or more records from a table. Use with extreme caution.

```sql
DELETE FROM customers
WHERE customer_id = 305;
```

⚠️ *Ensure you are not deleting active or referenced records. Always back up data before running delete operations.*

---

## ERP Use Cases

- 📦 Update inventory stock levels after a shipment
- 🏢 Add a new warehouse or location into the system
- 🛑 Remove discontinued products from the catalog
- 👤 Correct customer contact details
- 💰 Adjust pricing due to seasonal promotions or inflation

---

## Best Practices for DML

- 🔒 **Always back up** critical tables before running `UPDATE` or `DELETE`.
- 🔍 **Validate your conditions** with a `SELECT` query first:
  ```sql
  SELECT * FROM customers WHERE customer_id = 305;
  ```
- 🧪 Run queries in a **testing/staging environment** before applying to production.
- 📜 Use **transactions** (e.g., `BEGIN`, `COMMIT`, `ROLLBACK`) when running batch operations to ensure consistency and recoverability.

---

## Summary

DML operations are powerful tools that directly affect the business data inside an ERP system. With great power comes great responsibility: every change should be deliberate, tested, and ideally reversible. As you grow in your role, mastering DML will allow you to manage data confidently and accurately.

> 🧠 **Tip:** Document every DML operation you perform in production — for traceability and rollback planning.