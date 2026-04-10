# Component Diagram

Shows system component organization, interfaces, and dependencies.

## Key Elements

| Element | Syntax | Description |
|---|---|---|
| Component | `component "Name" as alias` or `[Name]` | Rectangle with component icon |
| Interface | `interface "Name" as alias` or `() "Name"` | Lollipop circle |
| Port | `port "Name" as alias` | Interaction point |
| Package | `package "Name" { }` | Container |
| Provided | `comp -- intf` | Component provides interface |
| Required | `comp ..> intf` | Component requires interface |
| Dependency | `[A] ..> [B]` | Dashed arrow |

## Interface Notations

```
  ()── Provided interface (lollipop) - "I provide this"
  ──)  Required interface (socket) - "I need this"
```

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Core component | `#dae8fc` (light blue) | Main business logic |
| Service component | `#d5e8d4` (light green) | Service layer |
| Data component | `#fff2cc` (light yellow) | Data access/storage |
| External component | `#e1d5e7` (light purple) | External/third-party |
| Interface | `#f5f5f5` (light gray) | Provided/required interfaces |
| Package | `#FAFAFA` (near white) | Subsystem boundaries |

## Example 1

E-commerce system with components, interfaces, and internal structure:

```plantuml
@startuml
skinparam component {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
  FontSize 12
}
skinparam package {
  BackgroundColor #FAFAFA
  BorderColor #cccccc
}
skinparam interface {
  BackgroundColor #f5f5f5
  BorderColor #999999
}

package "E-Commerce System" {
  package "Presentation Layer" {
    component [Web UI] #96CBFE
    component [Mobile API] #96CBFE
  }

  package "Business Layer" {
    component [Order Service] #A8D08D
    component [Payment Service] #A8D08D
    component [Catalog Service] #A8D08D
    component [User Service] #A8D08D
  }

  package "Data Layer" {
    component [Order Repository] #fff2cc
    component [Product Repository] #fff2cc
    component [User Repository] #fff2cc
  }
}

package "External" {
  component [Payment Gateway] #e1d5e7
  component [Email Provider] #e1d5e7
}

interface "REST API" as rest
interface "Order API" as orderApi
interface "Auth API" as authApi

[Web UI] -- rest
[Mobile API] -- rest

rest )-- [Order Service]
rest )-- [Catalog Service]

[Order Service] -- orderApi
[User Service] -- authApi

[Order Service] ..> [Payment Service] : uses
[Order Service] ..> [Order Repository] : persists
[Payment Service] ..> [Payment Gateway] : processes
[Catalog Service] ..> [Product Repository] : queries
[User Service] ..> [User Repository] : manages
[Order Service] ..> [Email Provider] : notifies

note right of [Order Service]
  Core business component
  coordinates payment,
  inventory, and fulfillment
end note
@enduml
```
