# 08. Core Design Patterns

### 📝 Core Summary
Design Patterns are typical solutions to common problems in software design. They are like pre-made blueprints you can customize to solve a recurring design problem in your code.

---

### 🔍 Detailed Explanation

#### 1. Categories
- **Creational**: How objects are created (e.g., Singleton, Factory).
- **Structural**: How classes and objects are composed (e.g., Adapter, Decorator).
- **Behavioral**: How objects communicate (e.g., Observer, Strategy).

#### 2. Top 3 Patterns for L3 Exams
1. **Singleton**: Ensures a class has only one instance and provides a global point of access to it.
2. **Factory Method**: Provides an interface for creating objects but allows subclasses to alter the type of objects that will be created.
3. **Observer**: Defines a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.

---

### 🏗️ Complete Applied Example: Singleton (Java)
**Scenario**: A Database Connection pool that should only have one instance.

```java
public class Database {
    private static Database instance;
    private Database() {} // Private constructor!
    
    public static Database getInstance() {
        if (instance == null) {
            instance = new Database();
        }
        return instance;
    }
}
```

---

### 💡 Exam Tips & Common Mistakes
- **Tip**: When justifying a pattern, use keywords like **"Decoupling"**, **"Flexibility"**, and **"Reusability"**.
- **Mistake**: Using a Singleton for everything. It's often considered an "anti-pattern" if overused because it introduces global state.
- **Mistake**: Confusing **Strategy** and **State** patterns. Strategy is about *how* you do something; State is about *what* an object is.

---

### ✍️ Short Training Exercise
**Question**: You are building a weather station. When the temperature changes, several displays (Phone App, LCD Screen, Web Dashboard) need to update. Which pattern should you use?
**Solution**: The **Observer Pattern**. The Weather Station is the *Subject*, and the displays are the *Observers*.
