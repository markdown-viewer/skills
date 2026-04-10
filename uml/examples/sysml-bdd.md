# SysML Block Definition Diagram (BDD)

Systems Modeling Language (SysML) extends UML for complex system design. Block Definition Diagrams show system structure with blocks, value types, and relationships.

## Key Elements

| Element | Syntax | Description |
|---|---|---|
| Block | `class "Name" <<block>>` | System building block |
| Constraint Block | `class "Name" <<constraint>>` | Mathematical constraint |
| Value Type | `class "Name" <<valueType>>` | Typed value |
| Flow Port | Attribute with `<<flowPort>>` | Data/material flow point |
| Composition | `*--` | Part-whole relationship |
| Reference | `o--` | Reference association |
| Compartments | Attributes grouped by region | values, parts, constraints |

## Block Compartments

| Compartment | Content |
|---|---|
| values | Value properties (typed attributes) |
| parts | Contained blocks (composition) |
| references | Referenced blocks |
| constraints | Constraint properties |
| operations | Block operations |
| flow ports | Flow interaction points |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| System block | `#dae8fc` (light blue) | Top-level system |
| Subsystem block | `#d5e8d4` (light green) | Subsystem components |
| Hardware block | `#fff2cc` (light yellow) | Physical/hardware parts |
| Constraint block | `#f8cecc` (light red) | Mathematical constraints |
| Value type | `#e1d5e7` (light purple) | Value types |
| Package | `#FAFAFA` (near white) | Model package container |

## Example 1

Vehicle system BDD showing blocks with compartments and constraint blocks:

```plantuml
@startuml
skinparam class {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
}
skinparam package {
  BackgroundColor #FAFAFA
  BorderColor #999999
}

package "<<bdd>> Vehicle System" {
  class "<<block>>\nVehicle" as vehicle #dae8fc {
    **values**
    weight : Mass
    maxSpeed : Velocity
    ----
    **parts**
    eng : Engine [1]
    trans : Transmission [1]
    w : Wheel [4]
    ----
    **constraints**
    {perf : PerformanceEq}
  }

  class "<<block>>\nEngine" as engine #d5e8d4 {
    **values**
    displacement : Volume
    horsepower : Power
    torque : Torque
    ----
    **flow ports**
    fuelIn : Fuel
    exhaustOut : Gas
  }

  class "<<block>>\nTransmission" as trans #d5e8d4 {
    **values**
    gearRatio : Real [6]
    type : TransType
    ----
    **operations**
    shiftUp()
    shiftDown()
  }

  class "<<block>>\nWheel" as wheel #fff2cc {
    **values**
    diameter : Length
    pressure : Pressure
    ----
    **flow ports**
    torqueIn : Torque
  }

  class "<<constraint>>\nPerformanceEq" as perfEq #f8cecc {
    **constraints**
    {accel = F / mass}
    {F = torque * gearRatio / radius}
    ----
    **parameters**
    accel : Acceleration
    F : Force
    mass : Mass
    torque : Torque
    gearRatio : Real
    radius : Length
  }

  class "<<valueType>>\nMass" as mass #e1d5e7 {
    unit = "kg"
  }

  class "<<valueType>>\nVelocity" as vel #e1d5e7 {
    unit = "m/s"
  }

  vehicle *-- "1" engine
  vehicle *-- "1" trans
  vehicle *-- "4" wheel
  vehicle --> perfEq : <<constrainedBy>>
  engine --> trans : drives
  trans --> wheel : transmits

  vehicle ..> mass : <<uses>>
  vehicle ..> vel : <<uses>>
}
@enduml
```
