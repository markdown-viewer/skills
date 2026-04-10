# Use Case Diagram

Describes system functional requirements and user interactions.

## Key Elements

- **Actor**: `actor "Name" as alias` — stick figure
- **Use Case**: `usecase "Name" as alias` or `(Name)` — ellipse
- **System boundary**: `rectangle "Name" { }` — container rectangle
- **Association**: `actor -- usecase` — solid line
- **Include**: `usecase1 ..> usecase2 : <<include>>` — dashed arrow
- **Extend**: `usecase1 ..> usecase2 : <<extend>>` — dashed arrow (arrow to base)
- **Generalization**: `actor1 --|> actor2` — hollow triangle arrow
- **Direction**: `left to right direction` — horizontal layout

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Primary actor | default | Main users |
| System actor | `#e1d5e7` (light purple) | External systems |
| Core use case | `#dae8fc` (light blue) | Primary functions |
| Secondary use case | `#d5e8d4` (light green) | Supporting functions |
| Admin use case | `#fff2cc` (light yellow) | Management functions |
| System boundary | `#FAFAFA` (near white) | System container |

## Example 1

E-commerce system use cases with multiple actor types and relationships:

```plantuml
@startuml
left to right direction

skinparam usecase {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  ArrowColor #333333
  FontName Arial
}
skinparam actor {
  FontName Arial
}
skinparam rectangle {
  BackgroundColor #FAFAFA
  BorderColor #cccccc
}

actor "Customer" as customer
actor "Registered\nCustomer" as regcust
actor "Admin" as admin
actor "Payment\nGateway" as pg #e1d5e7

regcust --|> customer

rectangle "E-Commerce System" {
  usecase "Browse Catalog" as UC1 #dae8fc
  usecase "Search Products" as UC2 #dae8fc
  usecase "View Product" as UC3 #dae8fc
  usecase "Add to Cart" as UC4 #d5e8d4
  usecase "Checkout" as UC5 #d5e8d4
  usecase "Process Payment" as UC6 #d5e8d4
  usecase "Track Order" as UC7 #d5e8d4
  usecase "Write Review" as UC8 #d5e8d4
  usecase "Manage Products" as UC9 #fff2cc
  usecase "Manage Orders" as UC10 #fff2cc
  usecase "View Reports" as UC11 #fff2cc
  usecase "Apply Coupon" as UC12 #d5e8d4
}

customer -- UC1
customer -- UC2
customer -- UC3
regcust -- UC4
regcust -- UC5
regcust -- UC7
regcust -- UC8

admin -- UC9
admin -- UC10
admin -- UC11

UC5 ..> UC6 : <<include>>
UC5 ..> UC12 : <<extend>>

UC6 -- pg
@enduml
```
