# TD 2: SOLID & Design Patterns (Solved)

This tutorial covers advanced design concepts and how to apply them to solve common software architecture problems.

---

## Exercise 1: Identifying SOLID Violations
**Code Snippet**:
```java
class Report {
    void generateReport() { /* logic */ }
    void saveToFile(String path) { /* logic */ }
    void printReport() { /* logic */ }
}
```
**Question**: Which SOLID principle is violated? How do you fix it?

### Solution:
- **Violation**: **Single Responsibility Principle (SRP)**. The `Report` class is doing too much: generating data, handling file I/O, and managing printing.
- **Fix**: Split into three classes: `ReportGenerator`, `ReportSaver`, and `ReportPrinter`.

---

## Exercise 2: Open/Closed Principle (OCP)
**Scenario**: You have a `DiscountCalculator` that calculates discounts for `Regular` and `VIP` customers using `if-else`. You want to add a `SummerSale` discount without modifying the calculator.

### Solution:
Use an interface `DiscountStrategy`.

```java
interface DiscountStrategy {
    double apply(double price);
}

class VIPDiscount implements DiscountStrategy {
    public double apply(double price) { return price * 0.8; }
}

class SummerDiscount implements DiscountStrategy {
    public double apply(double price) { return price * 0.9; }
}

class DiscountCalculator {
    private DiscountStrategy strategy;
    public void setStrategy(DiscountStrategy s) { this.strategy = s; }
    public double calculate(double price) { return strategy.apply(price); }
}
```

---

## Exercise 3: Pattern Selection
**Question**: Which pattern would you use for the following scenarios? Justify your answer.
1. You need to ensure only one instance of a `ConfigurationManager` exists.
2. You want to create different types of `UIButtons` (Windows, Mac, Linux) without specifying the concrete class in your code.
3. You want to notify a `Logger` and a `Dashboard` whenever a `Sensor` value changes.

### Solution:
1. **Singleton**: To prevent multiple conflicting configurations and save memory.
2. **Factory Method**: To decouple the client code from the specific OS implementations.
3. **Observer**: To allow multiple "listeners" to react to changes in the sensor without the sensor knowing who they are (decoupling).

---

## Exercise 4: Refactoring to Strategy Pattern
**Scenario**: A `PaymentProcessor` has a method `process(String type)`. Inside, it has a large `switch` statement for "CreditCard", "PayPal", and "Bitcoin".

### Solution:
1. Create a `PaymentMethod` interface.
2. Implement `CreditCardPayment`, `PayPalPayment`, etc.
3. The `PaymentProcessor` will now take a `PaymentMethod` object and call `method.pay()`. This follows **OCP** and **Strategy Pattern**.
