# 02. Use Case Diagrams (Cas d'utilisation)

### 📝 Core Summary
The Use Case diagram describes **what** the system does from the perspective of an external observer (Actor). it captures functional requirements.

---

### 🔍 Detailed Explanation

#### 1. Definitions
- **Actor**: An external entity (human, hardware, or another system) that interacts with the system.
- **Use Case**: A specific task or function the system performs to provide value to an actor.
- **System Boundary**: A box representing the limits of the application.

#### 2. When to use it in Exams?
When the subject asks you to "Identify the functional requirements" or "Model the interactions between users and the system."

---

### 🛠️ Key Elements and Notations
- **Relationships**:
  - **Include (`<<include>>`)**: Mandatory. Use Case A cannot happen without B (e.g., "Login" is included in "View Profile").
  - **Extend (`<<extend>>`)**: Optional. Use Case B happens only under certain conditions (e.g., "Apply Discount" extends "Checkout").
  - **Generalization**: An actor or use case is a specialized version of another.

---

### 🏗️ Complete Applied Example: Library System
**Scenario**: A student can borrow a book. To do this, they must be authenticated. Optionally, they can reserve a book if it's unavailable.

```mermaid
useCaseDiagram
    actor Student
    actor Librarian
    
    package "Library System" {
        usecase "Borrow Book" as UC1
        usecase "Authenticate" as UC2
        usecase "Reserve Book" as UC3
        usecase "Manage Books" as UC4
    }
    
    Student --> UC1
    UC1 ..> UC2 : <<include>>
    UC3 ..> UC1 : <<extend>>
    Librarian --> UC4
```

---

### 💡 Exam Tips & Common Mistakes
- **Tip**: Actors are **outside** the system boundary box.
- **Mistake**: Drawing arrows between actors. Actors do not talk to each other in this diagram; they only talk to the system.
- **Mistake**: Confusing `include` and `extend`. Remember: `include` is "always", `extend` is "sometimes".

---

### ✍️ Short Training Exercise
**Question**: In a "Withdraw Cash" use case, would "Print Receipt" be an `include` or `extend` relationship?
**Solution**: It is an **`extend`** relationship because the user can choose *not* to print a receipt.
