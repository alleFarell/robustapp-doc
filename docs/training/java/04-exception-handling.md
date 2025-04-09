# Exception Handling

Exception handling makes your programs more resilient and user-friendly.

## Basic Structure

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
} finally {
    System.out.println("Cleanup done");
}
```

## ERP Relevance
Handle input errors gracefully during data entry or file uploads.
