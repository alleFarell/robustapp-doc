# Java Basics

This module introduces the **fundamental building blocks** of the Java programming language. These core concepts are essential for developing reliable and maintainable ERP components, integrations, and utilities.

---

## Variables & Data Types

In Java, variables are containers that hold data values. Each variable has a **data type**, defining the kind of data it can store.

### Common Primitive Types:
- `int` – Whole numbers (e.g., `100`)
- `double` – Decimal numbers (e.g., `99.99`)
- `char` – A single character (e.g., `'A'`)
- `boolean` – True/false logic
- `String` – Sequence of characters (technically not primitive, but used like one)

```java
int quantity = 150;
double price = 129.99;
char category = 'B';
boolean isActive = true;
String productName = "Laptop";
```

---

## Control Flow Statements

Control flow allows your program to **make decisions** and **repeat actions**.

### Conditional Statements
- `if`, `else`, `else if` – Basic condition checks
- `switch` – Multi-branch selection

```java
if (stock < 100) {
    System.out.println("Reorder needed");
} else {
    System.out.println("Stock is sufficient");
}
```

### Looping Constructs
- `for` – Fixed iteration count
- `while` – Loops while condition is true
- `do-while` – Ensures at least one execution

```java
for (int i = 0; i < 10; i++) {
    System.out.println("Invoice #" + i);
}
```

---

## ERP-Relevant Use Cases

- 📦 **Inventory Threshold Automation:**
  Use `if` statements to trigger reorder alerts when stock is low.
- 🧾 **Batch Processing:**
  Use `for` or `while` loops to process large batches of transactions or records.
- 🧠 **Business Logic Mapping:**
  Use `switch` to map ERP codes to human-readable statuses.

---

## Best Practices

- ✅ Always initialize variables before use.
- 🧠 Choose the **right data type** — it affects memory usage and performance.
- 🧪 Keep control flow **readable and simple** — avoid deep nesting.
- 📛 Use `final` for constants or configuration values.

---

## Summary

Understanding variables and control structures is the first step toward building dynamic, interactive ERP features. Whether automating stock management or creating condition-based workflows, these fundamentals will serve as the core of your Java development skills.

> 🧠 **Tip:** Practice writing small programs that simulate real ERP tasks — like checking inventory, generating invoices, or applying discounts.