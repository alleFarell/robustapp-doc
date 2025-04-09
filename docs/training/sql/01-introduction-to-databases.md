# Introduction to Databases

Understanding databases is a fundamental skill for any Technical Consultant, especially when working with Enterprise Resource Planning (ERP) systems. ERP applications rely heavily on structured, relational databases to store and manage large volumes of data across different business functions.

## What is a Database?

A **database** is a systematic and organized collection of data that is electronically stored and accessed using computer systems. It enables users to efficiently store, retrieve, update, and manage information, ensuring data integrity, consistency, and accessibility.

Databases are the backbone of modern applications — from banking systems and e-commerce platforms to large-scale ERP solutions.

## Why Databases Matter in ERP

ERP systems integrate various business processes, such as finance, inventory, sales, and human resources. Each module relies on accurate, real-time data stored in the underlying database. As a Technical Consultant, your ability to understand and query this data is crucial for system customization, reporting, and troubleshooting.

## Types of Databases

- **Relational Databases (RDBMS):**
  - Organize data into structured tables with predefined relationships.
  - Use SQL (Structured Query Language) for data manipulation.
  - Examples: MySQL, PostgreSQL, Oracle Database, Microsoft SQL Server.
  - Commonly used in ERP systems due to their strong consistency and support for complex queries.

- **Non-relational Databases (NoSQL):**
  - Store data in flexible formats like documents, key-value pairs, graphs, or wide-columns.
  - Offer high scalability and performance for unstructured or semi-structured data.
  - Examples: MongoDB (document), Redis (key-value), Cassandra (wide-column), Neo4j (graph).
  - Used in scenarios where flexibility and speed are prioritized over strict consistency.

## Core Components of a Relational Database

- **Tables** – Represent entities such as customers, orders, or products.
- **Rows** – Each row is a unique record or instance of an entity.
- **Columns** – Define the attributes or fields of the entity (e.g., Customer Name, Email).

### Example

| CustomerID | Name        | Email                |
|------------|-------------|----------------------|
| 1          | Jane Smith  | jane@example.com     |
| 2          | John Doe    | john.doe@example.com |

## Primary Keys and Relationships

- A **Primary Key** is a unique identifier for each record in a table (e.g., CustomerID).
- **Foreign Keys** create relationships between tables (e.g., linking Orders to Customers).
- Understanding these relationships is essential for writing efficient and meaningful SQL queries.

## Conclusion

Grasping the structure and function of databases lays the groundwork for advanced topics such as SQL queries, data modeling, database design, and performance optimization. As you progress through this training, you'll gain hands-on experience working with real ERP data models to solidify these concepts.

> ✅ Tip: Always be mindful of how data flows between ERP modules and how relational integrity is maintained across tables.