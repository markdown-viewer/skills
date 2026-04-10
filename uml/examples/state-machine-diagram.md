# State Machine Diagram

Shows state changes of an object during its lifecycle.

## Key Elements

- **State**: `state "Name" as alias` — rounded rectangle
- **Initial state**: `[*] -->` — solid black circle
- **Final state**: `--> [*]` — circle with outer ring
- **Transition**: `State1 --> State2 : event` — labeled arrow
- **Composite state**: `state Name { ... }` — container with substates
- **Choice**: `state name <<choice>>` — diamond decision point
- **Fork/Join**: `state name <<fork>>` / `<<join>>` — bar for parallel
- **History**: `state name <<history>>` / `<<deepHistory>>`
- **Entry/Exit point**: `<<entryPoint>>` / `<<exitPoint>>`
- **Internal transition**: `State : entry / action` — inside state

## Recommended Colors

| State Type | Color | Usage |
|---|---|---|
| Pending/Idle | `#dae8fc` (light blue) | Waiting states |
| Active/Processing | `#fff2cc` (light yellow) | In-progress states |
| Success/Complete | `#d5e8d4` (light green) | Successful outcomes |
| Error/Cancel | `#f8cecc` (light red) | Error/failure states |
| Final/Archive | `#e1d5e7` (light purple) | Terminal states |
| Inline style | `#color;line:color;text:color` | Per-element colors |

## Example 1

Order processing state machine with composite states and parallel regions:

```plantuml
@startuml
skinparam state {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  ArrowColor #333333
  FontName Arial
  FontSize 12
  AttributeFontSize 10
}

[*] --> Pending

state Pending #dae8fc;line:6c8ebf : Order received\nAwaiting review

Pending --> Validating : Submit

state Validating #fff2cc;line:d6b656 {
  [*] --> CheckingInventory
  CheckingInventory --> CheckingPayment : Items available
  CheckingPayment --> [*] : Payment verified
  --
  [*] --> FraudCheck
  FraudCheck --> [*] : Passed
}

Validating --> Processing : Validation OK
Validating --> Cancelled : Validation failed

state Processing #d5e8d4;line:82b366 {
  [*] --> Picking
  Picking --> Packing : Items picked
  Packing --> ReadyToShip : Packed
}

Processing --> Shipped : Dispatched

state Shipped #e1d5e7;line:9673a6 : In transit\nTracking active

Shipped --> Delivered : Received
Shipped --> ReturnRequested : Customer return

state Delivered #d5e8d4;line:82b366
Delivered --> [*]

state Cancelled #f8cecc;line:b85450 : Order cancelled\nRefund initiated
Cancelled --> [*]

state ReturnRequested #f8cecc;line:b85450
ReturnRequested --> Refunded : Return approved

state Refunded #f8cecc;line:b85450
Refunded --> [*]

note right of Validating
  Parallel validation:
  inventory check and
  fraud detection run
  simultaneously
end note
@enduml
```
