# Java Collections Framework

The **Java Collections Framework (JCF)** provides a set of interfaces and classes for storing and manipulating groups of data efficiently. In ERP development, collections are used extensively to manage lists of transactions, users, inventory items, invoices, and more.

---

## Why Collections Matter

Traditional arrays in Java are fixed in size and lack many utility features. Collections allow for:

- Dynamic sizing
- Flexible data manipulation
- Advanced querying and sorting
- Efficient data access patterns

---

## Core Interfaces in the Collections API

| Interface | Description | Common Implementations |
|-----------|-------------|-------------------------|
| `List`    | Ordered collection (allows duplicates) | `ArrayList`, `LinkedList` |
| `Set`     | Unordered collection (no duplicates)   | `HashSet`, `TreeSet`      |
| `Map`     | Key-value pairs                        | `HashMap`, `TreeMap`      |

---

## Example: Using a List

```java
import java.util.*;

public class CustomerManager {
    public static void main(String[] args) {
        List<String> customers = new ArrayList<>();
        customers.add("John Doe");
        customers.add("Jane Smith");

        for (String customer : customers) {
            System.out.println(customer);
        }
    }
}
```

📦 *Great for managing customer names, product SKUs, or invoice numbers.*

---

## Example: Using a Map

```java
Map<String, Double> productPrices = new HashMap<>();
productPrices.put("Laptop", 999.99);
productPrices.put("Mouse", 25.50);

System.out.println("Laptop price: $" + productPrices.get("Laptop"));
```

🧾 *Perfect for storing key-value relationships like product names and prices.*

---

## ERP Use Cases

- 🧾 **Invoice Processing:** Use a `List` to track line items dynamically.
- 📦 **Inventory Mapping:** Use a `Map` to store stock levels by product ID.
- 👥 **User Roles:** Use a `Set` to store distinct access rights or roles.
- 💼 **Batch Updates:** Iterate through a `List` of changes to apply them to the database.

---

## Best Practices

- ✅ Choose the right collection type based on ordering, uniqueness, and lookup needs.
- 🔄 Always check for null or empty collections before iterating.
- ⚙️ Prefer generics (`List<Product>` instead of raw types) for type safety.
- 🔐 Use synchronized versions (e.g., `Collections.synchronizedList()`) if working in multi-threaded environments.

---

## Summary

Collections are essential for any Java developer working with dynamic data, especially in ERP systems where bulk records, mappings, and custom aggregations are common. Mastering the Java Collections Framework enables you to build efficient, scalable business logic.

> 🧠 **Tip:** Practice using `List`, `Set`, and `Map` in small ERP simulations — like tracking inventory changes or processing customer orders in bulk.