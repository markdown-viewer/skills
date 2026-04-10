# Class Diagram

Shows class structure with attributes, methods, and relationships between classes.

## Key Elements

- **Class**: `class ClassName { }` — define attributes and methods inside braces
- **Abstract class**: `abstract class Name` — italic name
- **Interface**: `interface Name` — with `<<interface>>` stereotype
- **Enumeration**: `enum Name` — list values inside braces
- **Visibility**: `+` public, `#` protected, `-` private, `~` package
- **Static member**: `{static}` modifier
- **Abstract method**: `{abstract}` modifier

## Relationships

| Relationship | Syntax | Description |
|---|---|---|
| Inheritance | `<\|--` | Hollow triangle (extends) |
| Realization | `..\|>` | Dashed + hollow triangle (implements) |
| Association | `-->` | Open arrow |
| Aggregation | `o--` | Hollow diamond (has-a) |
| Composition | `*--` | Filled diamond (owns) |
| Dependency | `..>` | Dashed open arrow (uses) |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Interface | `#d5e8d4` (light green) | Contract definitions |
| Abstract class | `#f8cecc` (light red) | Base classes |
| Concrete class | `#dae8fc` (light blue) | Regular classes |
| Enum | `#fff2cc` (light yellow) | Enumerations |
| Subclass | `#ffe6cc` (light orange) | Derived classes |
| Utility | `#e1d5e7` (light purple) | Utility/helper classes |

## Example 1

Zoo management system with interfaces, abstract class, enums, and various relationships:

```plantuml
@startuml
skinparam class {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  ArrowColor #333333
  FontName Arial
  FontSize 12
}
skinparam stereotypeCBackgroundColor #e1d5e7

interface IAnimal #d5e8d4;line:82b366 {
  +makeSound(): void
  +move(): void
}

abstract class Animal #f8cecc;line:b85450 {
  #name: String
  #age: int
  -{static} animalCount: int
  +{abstract} makeSound(): void
}

enum DietType #fff2cc;line:d6b656 {
  HERBIVORE
  CARNIVORE
  OMNIVORE
}

class Zoo #dae8fc;line:6c8ebf {
  -name: String
  -location: String
  +addAnimal(a: Animal): void
  +getAnimalCount(): int
}

class Cage #e1d5e7;line:9673a6 {
  -cageId: int
  -capacity: int
  +clean(): void
}

class Dog #ffe6cc;line:d79b00 {
  -breed: String
  -isVaccinated: boolean
  +makeSound(): void
}

class Cat #ffe6cc;line:d79b00 {
  -indoor: boolean
  -livesRemaining: int
  +makeSound(): void
}

Animal ..|> IAnimal
Animal ..> DietType : uses
Dog --|> Animal
Cat --|> Animal
Zoo "1" *-- "1..*" Cage
Zoo "1" o-- "0..*" Animal
Cage "1" --> "0..*" Dog : houses

note right of Animal
  Abstract class Animal
  implements IAnimal
  interface
end note
@enduml
```

## Example 2

Observer pattern with generic types and dependency relationships:

```plantuml
@startuml
skinparam class {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  ArrowColor #333333
  FontName Arial
}

interface Observer<T> #d5e8d4;line:82b366 {
  +update(event: T): void
}

interface Subject<T> #d5e8d4;line:82b366 {
  +subscribe(o: Observer<T>): void
  +unsubscribe(o: Observer<T>): void
  +notify(event: T): void
}

class EventBus<T> #dae8fc;line:6c8ebf {
  -observers: List<Observer<T>>
  +subscribe(o: Observer<T>): void
  +unsubscribe(o: Observer<T>): void
  +notify(event: T): void
}

class PriceAlert #ffe6cc;line:d79b00 {
  -threshold: double
  +update(event: PriceChange): void
}

class Dashboard #ffe6cc;line:d79b00 {
  -charts: List<Chart>
  +update(event: PriceChange): void
}

class StockService #fff2cc;line:d6b656 {
  -ticker: String
  -currentPrice: double
  +fetchPrice(): double
}

EventBus ..|> Subject
PriceAlert ..|> Observer
Dashboard ..|> Observer
EventBus o-- "*" Observer
StockService --> EventBus : publishes to
@enduml
```
