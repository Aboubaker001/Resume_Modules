# ⚡ GL Exam Cheatsheet: UML & SOLID

The ultimate one-page revision guide for the **Génie Logiciel** exam.

## 📊 UML Diagram Selection
| If the question asks for... | Use this Diagram |
| :--- | :--- |
| **Functional requirements** / What the system does | **Use Case Diagram** |
| **Static structure** / Classes, attributes, methods | **Class Diagram** |
| **Dynamic interaction** / Messages between objects | **Sequence Diagram** |
| **Workflow** / Logic, loops, and parallel tasks | **Activity Diagram** |
| **Object lifecycle** / Transitions between states | **State Machine Diagram** |

## 🏗️ SOLID Principles (One-Line Rules)
1. **S**ingle Responsibility: A class should have only **one reason to change**.
2. **O**pen/Closed: Software entities should be **open for extension**, but **closed for modification**.
3. **L**iskov Substitution: Subtypes must be **substitutable** for their base types.
4. **I**nterface Segregation: Many **specific interfaces** are better than one general-purpose interface.
5. **D**ependency Inversion: Depend on **abstractions**, not on concretions.

## 🗝️ UML Notation Reminders
- **Visibility**: `+` (Public), `-` (Private), `#` (Protected), `~` (Package).
- **Relationships**:
  - `───▶` Association (Simple link)
  - `───◇` Aggregation ("Has-a", weak)
  - `───◆` Composition ("Part-of", strong/life-dependent)
  - `───▷` Generalization (Inheritance)
  - `- - ▷` Realization (Interface implementation)
- **Multiplicities**: `1`, `0..*` (Many), `1..*` (At least one).

## 💡 Exam Strategy
- **Read the scenario twice**: Identify nouns (Classes) and verbs (Methods/Activities).
- **Justify your choices**: If you pick a pattern, explain *why* (e.g., "To allow adding new features without modifying existing code").
- **Mermaid Syntax Tip**: Use `graph TD` for flow, `classDiagram` for structure, and `sequenceDiagram` for interactions.
