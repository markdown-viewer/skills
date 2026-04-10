# Deployment Diagram

Shows physical deployment architecture of the system.

## Key Elements

| Element | Syntax | Description |
|---|---|---|
| Node | `node "Name" { }` | 3D box for execution environment |
| Device | `node "Name" <<device>>` | Physical hardware |
| Artifact | `artifact "Name"` | Deployable unit |
| Database | `database "Name"` | Data storage |
| Component | `component "Name"` | Software component |
| Cloud | `cloud "Name" { }` | Cloud infrastructure |
| Communication | `node1 -- node2 : protocol` | Network connection |
| Deploy | `artifact ..> node : <<deploy>>` | Deployment relationship |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Load balancer | `#dae8fc` (light blue) | Entry point / routing |
| Web server | `#d5e8d4` (light green) | Application servers |
| Database | `#fff2cc` (light yellow) | Data storage |
| Cache | `#ffe6cc` (light orange) | Caching layer |
| External service | `#e1d5e7` (light purple) | Third-party |
| Cloud container | `#F5F5F5` (light gray) | Cloud boundary |

## Example 1

Application server deployment with load balancer, web servers, and database cluster:

```plantuml
@startuml
skinparam node {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
}
skinparam database {
  BackgroundColor #fff2cc
  BorderColor #d6b656
}
skinparam cloud {
  BackgroundColor #F5F5F5
  BorderColor #cccccc
}
skinparam artifact {
  BackgroundColor #d5e8d4
  BorderColor #82b366
}

actor "Users" as users

cloud "AWS Cloud" {
  node "Load Balancer" as lb #dae8fc {
    artifact "Nginx Config" as ngconf
  }

  node "Web Server 1" as web1 #d5e8d4 {
    artifact "App v2.1" as app1
    artifact "Node.js 20" as node1
  }

  node "Web Server 2" as web2 #d5e8d4 {
    artifact "App v2.1" as app2
    artifact "Node.js 20" as node2
  }

  node "Data Tier" as data {
    database "PostgreSQL\nPrimary" as db1 #fff2cc
    database "PostgreSQL\nReplica" as db2 #fff2cc
    database "Redis Cache" as redis #ffe6cc
  }

  node "Storage" as storage {
    database "S3 Bucket" as s3 #fff2cc
  }
}

cloud "External" #e1d5e7 {
  node "CDN" as cdn #e1d5e7
  node "Email Service" as email #e1d5e7
}

users --> cdn : HTTPS
cdn --> lb : HTTPS
lb --> web1 : HTTP
lb --> web2 : HTTP
web1 --> db1 : JDBC
web2 --> db1 : JDBC
db1 --> db2 : Replication
web1 --> redis : TCP
web2 --> redis : TCP
web1 --> s3 : S3 API
web1 ..> email : SMTP

note right of data
  Primary-Replica setup
  with Redis caching
  for high availability
end note
@enduml
```
