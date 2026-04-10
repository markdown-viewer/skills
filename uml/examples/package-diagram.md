# Package Diagram

Shows the modular organization structure of a system.

## Key Elements

- **Package**: `package "Name" { }` — folder shape container
- **Nested package**: Package inside package
- **Dependency**: `pkg1 ..> pkg2` — dashed arrow
- **Import**: `pkg1 ..> pkg2 : <<import>>` — package imports another
- **Access**: `pkg1 ..> pkg2 : <<access>>` — restricted access
- **Merge**: `pkg1 ..> pkg2 : <<merge>>` — package merge
- **Use**: `pkg1 ..> pkg2 : <<use>>` — usage dependency
- **Stereotype**: `package "Name" <<Node>>` — package with stereotype shape

## Package Stereotypes (Shapes)

| Stereotype | Syntax | Shape |
|---|---|---|
| Folder | `package "Name"` | Default folder tab |
| Rectangle | `package "Name" <<Rectangle>>` | Plain rectangle |
| Frame | `package "Name" <<Frame>>` | Frame with label |
| Cloud | `package "Name" <<Cloud>>` | Cloud shape |
| Database | `package "Name" <<Database>>` | Cylinder |
| Node | `package "Name" <<Node>>` | 3D box |

## Recommended Colors

| Layer | Color | Usage |
|---|---|---|
| Presentation | `#96CBFE` (sky blue) | UI layer |
| Application | `#A8D08D` (sage green) | Service/business layer |
| Domain | `#fff2cc` (light yellow) | Domain model |
| Infrastructure | `#e1d5e7` (light purple) | Data/external access |
| Shared/Common | `#ffe6cc` (light orange) | Cross-cutting concerns |

## Example 1

E-commerce system module structure with layered architecture:

```plantuml
@startuml
skinparam package {
  BackgroundColor #FAFAFA
  BorderColor #999999
  FontName Arial
  FontSize 13
  FontStyle bold
}
skinparam arrow {
  Color #333333
}

package "Presentation Layer" #96CBFE {
  package "Web UI" as webui #dae8fc {
  }
  package "Mobile API" as mobile #dae8fc {
  }
  package "Admin Console" as admin #dae8fc {
  }
}

package "Application Layer" #A8D08D {
  package "Order Service" as ordersvc #d5e8d4 {
  }
  package "Catalog Service" as catsvc #d5e8d4 {
  }
  package "User Service" as usersvc #d5e8d4 {
  }
  package "Payment Service" as paysvc #d5e8d4 {
  }
}

package "Domain Layer" #fff2cc {
  package "Order Model" as ordermod {
  }
  package "Product Model" as prodmod {
  }
  package "User Model" as usermod {
  }
}

package "Infrastructure Layer" #e1d5e7 {
  package "Persistence" as persist {
  }
  package "Messaging" as messaging {
  }
  package "External APIs" as extapi {
  }
}

package "Shared" #ffe6cc {
  package "Common Utils" as utils {
  }
  package "Security" as security {
  }
}

webui ..> ordersvc : <<use>>
webui ..> catsvc : <<use>>
mobile ..> ordersvc : <<use>>
admin ..> usersvc : <<use>>

ordersvc ..> ordermod : <<import>>
catsvc ..> prodmod : <<import>>
usersvc ..> usermod : <<import>>
paysvc ..> ordermod : <<access>>

ordermod ..> utils : <<use>>
persist ..> ordermod : <<import>>
persist ..> prodmod : <<import>>
messaging ..> utils : <<use>>
extapi ..> security : <<use>>
@enduml
```

## Example 2

Clean Architecture with stereotype shapes:

```plantuml
@startuml
skinparam package {
  BackgroundColor #FAFAFA
  BorderColor #999999
  FontName Arial
  FontSize 13
}

package "Entities" <<Rectangle>> #fff2cc {
  package "User" as ent_user {}
  package "Invoice" as ent_inv {}
}

package "Use Cases" <<Rectangle>> #d5e8d4 {
  package "CreateUser" as uc_user {}
  package "GenerateInvoice" as uc_inv {}
}

package "Adapters" <<Frame>> #dae8fc {
  package "REST Controller" as ctrl {}
  package "DB Gateway" as gw {}
}

package "Frameworks" <<Cloud>> #e1d5e7 {
  package "Express.js" as express {}
  package "PostgreSQL" as pg {}
}

ctrl ..> uc_user : <<use>>
ctrl ..> uc_inv : <<use>>
uc_user ..> ent_user : <<import>>
uc_inv ..> ent_inv : <<import>>
express ..> ctrl : <<use>>
gw ..> ent_user : <<import>>
pg ..> gw : <<use>>
@enduml
```
