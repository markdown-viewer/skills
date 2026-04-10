# Communication Diagram

Shows interactions between objects, emphasizing structural organization and numbered message sequences.

## Key Elements

| Element | Syntax | Description |
|---|---|---|
| Object | `participant "name" as alias` or `object "name" as alias` | Object instance |
| Actor | `actor "name" as alias` | External participant |
| Boundary | `boundary "name" as alias` | UI/interface object |
| Control | `control "name" as alias` | Controller object |
| Entity | `entity "name" as alias` | Data/database object |
| Link | `A -> B` | Association between objects |
| Numbered message | `A -> B : 1: message` | Sequential message |

## Message Numbering

- **Sequential**: `1, 2, 3...` — messages in order
- **Nested**: `1.1, 1.2, 1.1.1...` — sub-messages within a call
- **Concurrent**: `1a, 1b` — parallel messages at same level

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Boundary | `#96CBFE` (sky blue) | UI/interface objects |
| Control | `#A8D08D` (sage green) | Controller objects |
| Entity | `#fff2cc` (light yellow) | Data objects |
| Actor | default | External participants |
| Database | `#F4B183` (peach) | Data storage |

## Example 1

E-commerce checkout process with numbered message sequences:

```plantuml
@startuml
skinparam participant {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
}
skinparam boundary {
  BackgroundColor #96CBFE
  BorderColor #6c8ebf
}
skinparam control {
  BackgroundColor #A8D08D
  BorderColor #82b366
}
skinparam entity {
  BackgroundColor #fff2cc
  BorderColor #d6b656
}

actor "Customer" as cust
boundary "Checkout UI" as ui #96CBFE
control "OrderController" as ctrl #A8D08D
entity "Order" as order #fff2cc
entity "Payment" as pay #fff2cc
database "OrderDB" as db #F4B183

cust -> ui : 1: checkout()
ui -> ctrl : 1.1: createOrder()
ctrl -> order : 1.1.1: new Order()
ctrl -> pay : 1.1.2: processPayment()
pay -> db : 1.1.2.1: savePayment()
db --> pay : 1.1.2.2: confirmation
ctrl -> order : 1.1.3: confirmOrder()
order -> db : 1.1.3.1: persist()
ctrl --> ui : 1.2: orderConfirmation
ui --> cust : 1.3: displayConfirmation

note over ctrl
  Controller coordinates
  order creation and
  payment processing
end note
@enduml
```
