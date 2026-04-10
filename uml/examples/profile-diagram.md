# Profile Diagram

Shows UML extension mechanisms, defining custom stereotypes to extend UML metaclasses.

## Key Elements

| Element | Syntax | Description |
|---|---|---|
| Profile | `package "Name" <<Profile>> { }` | Profile container |
| Metaclass | `class "Name" <<Metaclass>>` | Base UML metaclass |
| Stereotype | `class "Name" <<Stereotype>>` | Custom stereotype definition |
| Extension | `Stereotype --|> Metaclass` | Stereotype extends metaclass |
| Tagged value | Attributes inside stereotype class | Additional properties |
| Constraint | `note` attached to stereotype | OCL or natural language rules |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Metaclass | `#dae8fc` (light blue) | Standard UML metaclasses |
| Stereotype | `#d5e8d4` (light green) | Custom stereotype definitions |
| Profile | `#FAFAFA` (near white) | Profile container |
| Constraint | `#fff2cc` (light yellow) | Rules and constraints |
| Applied profile | `#e1d5e7` (light purple) | Profile application |

## Example 1

Smart device profile with stereotypes extending UML metaclasses:

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

package "<<Profile>>\nSmartDeviceProfile" {
  class "<<Metaclass>>\nClass" as mc_class #dae8fc
  class "<<Metaclass>>\nComponent" as mc_comp #dae8fc
  class "<<Metaclass>>\nProperty" as mc_prop #dae8fc

  class "<<Stereotype>>\nSensor" as st_sensor #d5e8d4 {
    sensorType: String
    samplingRate: int
    unit: String
  }

  class "<<Stereotype>>\nActuator" as st_act #d5e8d4 {
    actuatorType: String
    responseTime: int
  }

  class "<<Stereotype>>\nGateway" as st_gw #d5e8d4 {
    protocol: String
    maxConnections: int
  }

  class "<<Stereotype>>\nMeasurement" as st_meas #d5e8d4 {
    precision: double
    range: String
  }

  st_sensor --|> mc_class
  st_act --|> mc_class
  st_gw --|> mc_comp
  st_meas --|> mc_prop
}

note bottom of st_sensor #fff2cc
  Constraint:
  samplingRate > 0
  unit must be SI
end note

package "<<apply>>\nSmartHome Model" #e1d5e7 {
  class "<<Sensor>>\nTemperatureSensor" as ts {
    +readTemp(): double
  }

  class "<<Actuator>>\nThermostat" as therm {
    +setTarget(t: double)
  }

  class "<<Gateway>>\nHomeHub" as hub {
    +registerDevice()
  }

  hub --> ts : monitors
  hub --> therm : controls
}
@enduml
```
