# Object-Oriented Programming in Java

Java is built around the principles of **Object-Oriented Programming (OOP)** — a paradigm that models software based on real-world entities. Mastering OOP is essential for building maintainable, scalable, and modular ERP applications.

---

## Why OOP Matters in ERP

ERP systems consist of entities like **Customers**, **Orders**, **Invoices**, and **Products**. Using OOP allows developers to represent these entities as **objects**, encapsulate their behavior, and build flexible business logic.

---

## Core OOP Concepts

### 1. **Class & Object**
- A **class** defines a blueprint for objects.
- An **object** is an instance of a class.

```java
class Product {
    String name;
    double price;

    void display() {
        System.out.println(name + ": $" + price);
    }
}

Product item = new Product();
item.name = "Laptop";
item.price = 999.99;
item.display();
```

---

### 2. **Encapsulation**
Encapsulation hides internal state and requires all interaction to be performed through an object's methods.

```java
class Customer {
    private String name;

    public void setName(String name) {
        this.name = name;
    }

    public String getName() {
        return this.name;
    }
}
```

🔐 *Improves data security and integrity in ERP modules.*

---

### 3. **Inheritance**
Allows a class to inherit fields and methods from another class.

```java
class Employee {
    String name;
}

class Manager extends Employee {
    int teamSize;
}
```

🧬 *Used to share common functionality between ERP entities (e.g., Users → Employees → Managers).*

---

### 4. **Polymorphism**
Allows one interface to be used for different data types or implementations.

```java
class Report {
    void generate() {
        System.out.println("Generating report...");
    }
}

class SalesReport extends Report {
    void generate() {
        System.out.println("Generating sales report...");
    }
}
```

🔁 *Improves code flexibility and extensibility — useful for reporting modules.*

---

### 5. **Abstraction & Interfaces**
Hide unnecessary details and expose only the essential parts. Interfaces define contracts for what a class must do.

```java
interface Payable {
    void processPayment();
}

class Invoice implements Payable {
    public void processPayment() {
        // implementation
    }
}
```

🎯 *Used for defining ERP component behaviors like “Payable,” “Exportable,” or “Auditable.”*

---

## ERP Use Cases

- 🧾 **Class-based modeling** for Customers, Products, and Orders
- ⚙️ **Inheritance and interfaces** for reusable business logic
- 🔄 **Polymorphic methods** for processing different types of transactions
- 🧩 **Encapsulation** for securing sensitive data (e.g., payroll, tax information)

---

## Summary

OOP is more than a coding style — it’s a methodology for building modular, reusable, and efficient ERP systems. With strong object modeling, your Java-based ERP components will be easier to maintain, extend, and scale.

> 🧠 **Tip:** Think in terms of “objects” that reflect your ERP's real-world entities — and then add logic through methods that align with business rules.