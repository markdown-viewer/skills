# Object Diagram

Shows instances (objects) and their attribute values at a specific point in time.

## Key Elements

| Element | Syntax | Description |
|---|---|---|
| Object | `object "name : Class" as alias` | Instance with class type |
| Attribute | `alias : attrName = "value"` | Attribute value assignment |
| Link | `obj1 --> obj2` | Association between instances |
| Link label | `obj1 --> obj2 : label` | Named association |
| Map | `map "Name" as alias { key => value }` | Key-value container |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Entity object | `#dae8fc` (light blue) | Domain objects |
| Value object | `#d5e8d4` (light green) | Value types |
| Reference object | `#fff2cc` (light yellow) | Referenced entities |
| Collection | `#ffe6cc` (light orange) | Lists/sets |
| Config object | `#e1d5e7` (light purple) | Configuration |

## Example 1

University system snapshot showing students, courses, and their relationships:

```plantuml
@startuml
skinparam object {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
  AttributeFontSize 11
}

object "alice : Student" as alice #dae8fc {
  studentId = "S2024001"
  name = "Alice Johnson"
  gpa = 3.8
  major = "Computer Science"
}

object "bob : Student" as bob #dae8fc {
  studentId = "S2024002"
  name = "Bob Smith"
  gpa = 3.5
  major = "Mathematics"
}

object "cs101 : Course" as cs101 #d5e8d4 {
  courseId = "CS-101"
  title = "Intro to Programming"
  credits = 3
  semester = "Fall 2024"
}

object "math201 : Course" as math201 #d5e8d4 {
  courseId = "MATH-201"
  title = "Linear Algebra"
  credits = 4
  semester = "Fall 2024"
}

object "prof1 : Professor" as prof1 #fff2cc {
  staffId = "P1001"
  name = "Dr. Carol Lee"
  department = "Computer Science"
}

object "addr1 : Address" as addr1 #e1d5e7 {
  street = "123 Campus Dr"
  city = "Springfield"
  zip = "62701"
}

alice --> cs101 : enrolled
alice --> math201 : enrolled
bob --> cs101 : enrolled
bob --> math201 : enrolled
prof1 --> cs101 : teaches
alice --> addr1 : lives at
bob --> addr1 : lives at
@enduml
```

## Example 2

E-commerce order snapshot with map and linked objects:

```plantuml
@startuml
skinparam object {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
  AttributeFontSize 11
}

object "order42 : Order" as order #dae8fc {
  orderId = "ORD-042"
  status = "Shipped"
  total = "$149.97"
}

object "item1 : LineItem" as item1 #d5e8d4 {
  product = "Wireless Mouse"
  qty = 2
  price = "$24.99"
}

object "item2 : LineItem" as item2 #d5e8d4 {
  product = "USB-C Hub"
  qty = 1
  price = "$99.99"
}

map "shipping : ShippingInfo" as ship #ffe6cc {
  carrier => "FedEx"
  tracking => "FX123456"
  eta => "2024-12-20"
}

object "cust7 : Customer" as cust #fff2cc {
  name = "Jane Doe"
  email = "jane@example.com"
}

order *-- item1
order *-- item2
order --> ship : shipped via
order --> cust : placed by
@enduml
```
