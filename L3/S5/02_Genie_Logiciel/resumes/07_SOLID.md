# 07. SOLID Principles

### 📝 Core Summary
SOLID is an acronym for five design principles intended to make software designs more understandable, flexible, and maintainable.

---

### 🔍 Detailed Explanation

#### 1. The Five Principles
- **S: Single Responsibility (SRP)**: A class should do one thing and have only one reason to change.
- **O: Open/Closed (OCP)**: You should be able to add new functionality without changing existing code.
- **L: Liskov Substitution (LSP)**: Subclasses should be able to replace their parent classes without breaking the program.
- **I: Interface Segregation (ISP)**: Don't force a class to implement methods it doesn't use. Split large interfaces into smaller ones.
- **D: Dependency Inversion (DIP)**: High-level modules should not depend on low-level modules. Both should depend on abstractions (interfaces).

#### 2. When to use it in Exams?
When asked to "Critique this code" or "Refactor this design to be more maintainable."

---

### 🏗️ Complete Applied Example: SRP Violation & Fix
**Violation**: A `User` class that handles both user data and database saving.
```java
class User {
    void saveToDB() { /* ... */ } // WRONG: User shouldn't know about DB
}
```
**Fix**: Separate the concerns.
```java
class User { /* data only */ }
class UserRepository {
    void save(User u) { /* DB logic */ } // RIGHT
}
```

---

### 💡 Exam Tips & Common Mistakes
- **Tip**: If you see a giant `switch` statement or many `if-else` blocks checking for types, it's likely a violation of the **Open/Closed Principle**.
- **Mistake**: Thinking SOLID only applies to Java. These are universal object-oriented principles.
- **Mistake**: Over-engineering. Don't apply SOLID if the system is extremely simple, but in exams, always assume the professor wants to see these principles applied.

---

### ✍️ Short Training Exercise
**Question**: Which principle is violated if a `Bird` interface has a `fly()` method, but an `Ostrich` class (which can't fly) is forced to implement it?
**Solution**: **Interface Segregation Principle (ISP)** (and potentially Liskov Substitution). The fix is to have a separate `Flyable` interface.
