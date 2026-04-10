# Technology Infrastructure

Technology layer view: servers, networks, system software, and their hosting relationships.

## Key Elements

| Layer | Macros Used |
|-------|-------------|
| Technology | `Technology_Device`, `Technology_Node`, `Technology_SystemSoftware`, `Technology_Artifact`, `Technology_CommunicationNetwork`, `Technology_Service` |

## Example

Three-tier deployment: load balancer → app cluster → database cluster with shared storage network:

```plantuml
@startuml
!include <archimate/Archimate>

Technology_CommunicationNetwork(inet, "Internet")
Technology_CommunicationNetwork(lan, "Internal LAN")
Technology_CommunicationNetwork(san, "Storage Network")

rectangle "DMZ" {
  Technology_Device(lb, "Load Balancer")
  Technology_SystemSoftware(nginx, "Nginx")
}

rectangle "Application Tier" {
  Technology_Node(app1, "App Server 1")
  Technology_Node(app2, "App Server 2")
  Technology_SystemSoftware(jvm1, "JVM Runtime")
  Technology_SystemSoftware(jvm2, "JVM Runtime")
  Technology_Artifact(war, "app.war")
}

rectangle "Database Tier" {
  Technology_Device(dbPrimary, "DB Primary")
  Technology_Device(dbReplica, "DB Replica")
  Technology_SystemSoftware(pg1, "PostgreSQL")
  Technology_SystemSoftware(pg2, "PostgreSQL")
  Technology_Device(nas, "NAS Storage")
}

Rel_Association(inet, lb, "")
Rel_Assignment(lb, nginx, "")
Rel_Association(lb, lan, "")

Rel_Association(lan, app1, "")
Rel_Association(lan, app2, "")
Rel_Assignment(app1, jvm1, "")
Rel_Assignment(app2, jvm2, "")
Rel_Assignment(jvm1, war, "")
Rel_Assignment(jvm2, war, "")

Rel_Association(lan, dbPrimary, "")
Rel_Assignment(dbPrimary, pg1, "")
Rel_Assignment(dbReplica, pg2, "")
Rel_Serving(dbReplica, dbPrimary, "replication")
Rel_Association(san, dbPrimary, "")
Rel_Association(san, dbReplica, "")
Rel_Association(san, nas, "")
@enduml
```

## Pattern Notes

1. **Device vs Node** — `Technology_Device` for physical hardware (load balancer, DB servers, NAS); `Technology_Node` for logical compute units (app servers)
2. **SystemSoftware** — `Technology_SystemSoftware` for runtime environments (Nginx, JVM, PostgreSQL) assigned to their host
3. **Artifact** — `Technology_Artifact` for deployable units (app.war) assigned to the runtime
4. **Communication Networks** — `Technology_CommunicationNetwork` for network segments (Internet, LAN, SAN); elements connect via `Rel_Association`
5. **Replication** — `Rel_Serving` between DB replica and primary shows data replication relationship
6. **Zone grouping** — `rectangle "DMZ"`, `"Application Tier"`, `"Database Tier"` represent network security zones
