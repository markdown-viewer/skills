# Mermaid Syntax Reference

Detailed syntax rules for advanced diagram types. Load this when you need specific syntax details.

---

## Sequence Diagram Syntax

### Messages
```
->>   Solid line with arrow
-->>  Dashed line with arrow
-)    Solid line with open arrow
--)   Dashed line with open arrow
```

### Activation & Notes
```mermaid
sequenceDiagram
    participant A
    participant B
    A->>+B: Request (activates B)
    Note right of B: Processing
    B-->>-A: Response (deactivates B)
    Note over A,B: Both involved
```

### Loops & Conditions
```mermaid
sequenceDiagram
    loop Every minute
        A->>B: Heartbeat
    end
    alt Success
        B-->>A: OK
    else Failure
        B-->>A: Error
    end
    opt Optional
        A->>B: Extra call
    end
```

---

## Class Diagram Syntax

### Relationships
```
<|--  Inheritance
*--   Composition
o--   Aggregation
-->   Association
--    Link (solid)
..>   Dependency
..|>  Realization
```

### Class Definition
```mermaid
classDiagram
    class Animal {
        +String name
        +int age
        +makeSound() void
        -privateMethod() int
        #protectedMethod()
    }
    Animal <|-- Dog
    Animal <|-- Cat
```

---

## ER Diagram Syntax

### Cardinality
```
||--||  One to one
||--o{  One to many
}o--o{  Many to many
||--o|  One to zero or one
```

### Example
```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE_ITEM : contains
    PRODUCT }|--o{ LINE_ITEM : "ordered in"
```

---

## Gantt Chart Syntax

```mermaid
gantt
    title Project Schedule
    dateFormat YYYY-MM-DD
    section Phase 1
        Task 1: a1, 2024-01-01, 30d
        Task 2: a2, after a1, 20d
    section Phase 2
        Task 3: 2024-02-15, 25d
        Milestone: milestone, m1, 2024-03-15, 0d
```

### Task Status
```
done     Completed task
active   Current task
crit     Critical path
```

---

## User Journey Syntax

```mermaid
journey
    title User Shopping Experience
    section Browse
        Visit website: 5: User
        Search product: 4: User
    section Purchase
        Add to cart: 5: User
        Checkout: 3: User
        Payment: 4: User
```

Score: 1 (bad) to 5 (great)

---

## XY Chart Syntax

```mermaid
xychart
    title "Monthly Sales"
    x-axis [Jan, Feb, Mar, Apr]
    y-axis "Revenue" 0 --> 150
    bar [65, 78, 52, 91]
    line [65, 78, 52, 91]
```

---

## Kanban Syntax

```mermaid
kanban
  Todo
    [Design System]
  InProgress
    [Implement Feature]
  Done
    [Setup CI/CD]
```

---

## Layout & Styling

### Directions
- `TB` / `TD` — Top to Bottom (default)
- `LR` — Left to Right
- `RL` — Right to Left
- `BT` — Bottom to Top

### Node Styling
```mermaid
flowchart TD
    A[Node A]
    B[Node B]
    style A fill:#90EE90,stroke:#333,stroke-width:2px
    style B fill:#ff6b6b,color:white
```

### Class Definitions
```mermaid
flowchart TD
    A:::success --> B:::warning
    classDef success fill:#2ECC71,color:white
    classDef warning fill:#F39C12,color:white
```

### Link Styling
```mermaid
flowchart TD
    A --> B
    linkStyle 0 stroke:#ff0000,stroke-width:2px
```

---

## Subgraph Advanced

### Nested Subgraphs
```mermaid
flowchart TB
    subgraph outer["Outer Group"]
        subgraph inner["Inner Group"]
            A --> B
        end
        C --> inner
    end
```

### Subgraph Direction
```mermaid
flowchart LR
    subgraph sub["Vertical Inside"]
        direction TB
        A --> B --> C
    end
    D --> sub
```
