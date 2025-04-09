# Working with Files in Java

**File I/O (Input/Output)** allows Java programs to read from and write to external files. In ERP systems, this is essential for tasks like importing transactional data, generating reports, processing logs, or interfacing with third-party systems.

---

## Why File I/O Matters in ERP

ERP systems frequently deal with file operations:
- Importing inventory updates from suppliers (CSV, XML)
- Generating printable reports or invoices (TXT, PDF)
- Integrating with legacy systems via flat files
- Archiving daily transaction logs

---

## Reading a File

```java
import java.io.*;

public class FileReaderExample {
    public static void main(String[] args) throws IOException {
        BufferedReader reader = new BufferedReader(new FileReader("input.txt"));
        String line;
        while ((line = reader.readLine()) != null) {
            System.out.println(line);
        }
        reader.close();
    }
}
```

📥 *This reads a text file line by line and prints each line to the console.*

---

## Writing to a File

```java
import java.io.*;

public class FileWriterExample {
    public static void main(String[] args) throws IOException {
        BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"));
        writer.write("ERP file export complete.");
        writer.newLine();
        writer.write("Timestamp: " + System.currentTimeMillis());
        writer.close();
    }
}
```

📤 *Useful for generating logs, summaries, or exports.*

---

## Modern Approach (Java NIO)

```java
import java.nio.file.*;
import java.util.*;

List<String> lines = Files.readAllLines(Paths.get("input.txt"));
lines.forEach(System.out::println);
```

⚡ *Simplifies file handling and reduces boilerplate code.*

---

## ERP Scenarios

- 📈 **Sales Report Parsing:** Read monthly reports and extract KPIs.
- 📦 **Inventory Import:** Load product quantities from supplier feeds.
- 🧾 **Audit Logging:** Write logs for transaction success/failure tracking.
- 🧷 **Data Archiving:** Export data snapshots for backup and compliance.

---

## Best Practices

- ✅ Always **close streams** (`.close()` or use try-with-resources).
- ⚠️ Handle `IOException` with appropriate messages and recovery logic.
- 🗂 Use relative paths or configuration-based file paths for portability.
- 🧪 Validate file content before processing (e.g., format, headers).

---

## Summary

File handling in Java is a foundational skill for ERP developers, enabling data interchange and batch processing. Whether importing records or exporting logs, efficient file operations can drastically improve business process automation.

> 🧠 **Tip:** Combine file reading with Java Collections to parse and transform ERP data on the fly.