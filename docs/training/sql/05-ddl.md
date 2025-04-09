# Data Definition Language (DDL)

**Data Definition Language (DDL)** consists of SQL commands used to create and modify the structure of database objects like tables, columns, indexes, and constraints. In an ERP environment, DDL is crucial for customizing schemas, preparing for migrations, and supporting system upgrades.

As a Technical Consultant, understanding DDL enables you to tailor the database to match business requirements without compromising data integrity.

---

## CREATE TABLE – Define New Structures

Used to create new tables in the database.

```sql
CREATE TABLE branches (
  branch_id INT PRIMARY KEY,
  branch_name VARCHAR(100),
  city VARCHAR(100)
);
```

🏗️ *Useful when creating new entities such as warehouses, departments, or operational regions.*

---

## ALTER TABLE – Modify Existing Structures

Used to add, drop, or modify columns and constraints in existing tables.

```sql
ALTER TABLE customers
ADD COLUMN loyalty_points INT DEFAULT 0;
```

🧱 *Essential for extending ERP modules with custom fields (e.g., adding loyalty programs, tax IDs, or secondary contacts).*

---

## DROP TABLE – Remove a Table

Deletes an entire table and all its data. Use with extreme caution.

```sql
DROP TABLE old_transactions;
```

⚠️ *Often used to clean up temporary or staging tables after data migration or testing.*

---

## ERP Use Cases for DDL

- 🛠️ Add custom fields to accommodate country-specific or client-specific attributes
- 🔄 Create temporary staging tables for data migration or ETL processes
- 🧩 Modify data types to align with third-party system integrations
- ⬆️ Adjust schema during ERP system upgrades

---

## Best Practices for Using DDL

- ✅ Always take **full database backups** before structural changes
- 🧪 Perform DDL changes in **staging environments** first
- 📋 Review dependencies — changing a table might affect reports, integrations, or applications
- 🧭 Use **version control** or **change logs** to track schema modifications over time
- 💡 Favor `ALTER TABLE` over `DROP + CREATE` to retain existing data

---

## Summary

DDL forms the blueprint of your ERP system's data architecture. Proper use of `CREATE`, `ALTER`, and `DROP` commands allows you to evolve and extend ERP functionality as business needs grow — all while maintaining structure, reliability, and integrity.

> 🧠 **Tip:** When customizing ERP schemas, always confirm your changes align with the core system's upgrade path to avoid future compatibility issues.