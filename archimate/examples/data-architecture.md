# Data Architecture

Data ownership, data flows, and access patterns across applications with data objects and access relationships.

## Key Elements

| Layer | Macros Used |
|-------|-------------|
| Business | `Business_Actor`, `Business_Process` |
| Application | `Application_Component`, `Application_DataObject`, `Application_Service` |

## Example

Customer data platform: data producers, data lake, and consuming analytics services with access controls:

```plantuml
@startuml
!include <archimate/Archimate>

rectangle "Data Producers" {
  Application_Component(web, "Web App")
  Application_Component(mobile, "Mobile App")
  Application_Component(erp, "ERP System")
  Application_Component(iot, "IoT Gateway")
}

rectangle "Data Platform" {
  Application_Service(ingest, "Ingestion Service")
  Application_Service(catalog, "Data Catalog")
  Application_DataObject(rawData, "Raw Data Lake")
  Application_DataObject(curated, "Curated Datasets")
  Application_DataObject(masterData, "Master Data")
}

rectangle "Data Consumers" {
  Application_Component(bi, "BI Dashboard")
  Application_Component(ml, "ML Platform")
  Application_Component(report, "Reporting Service")
  Business_Actor(analyst, "Data Analyst")
  Business_Actor(scientist, "Data Scientist")
}

rectangle "Governance" {
  Business_Process(quality, "Data Quality Process")
  Business_Process(lineage, "Data Lineage Tracking")
  Business_Actor(steward, "Data Steward")
}

Rel_Access_w(web, ingest, "events")
Rel_Access_w(mobile, ingest, "events")
Rel_Access_w(erp, ingest, "batch")
Rel_Access_w(iot, ingest, "stream")

Rel_Access_w(ingest, rawData, "writes")
Rel_Flow(rawData, curated, "transform")
Rel_Flow(curated, masterData, "enrich")
Rel_Serving(catalog, curated, "indexes")

Rel_Access_r(bi, curated, "reads")
Rel_Access_r(ml, rawData, "reads")
Rel_Access_r(report, masterData, "reads")
Rel_Assignment(analyst, bi, "uses")
Rel_Assignment(scientist, ml, "uses")

Rel_Assignment(steward, quality, "owns")
Rel_Assignment(steward, lineage, "owns")
Rel_Serving(quality, curated, "validates")
Rel_Serving(lineage, catalog, "tracks")
@enduml
```

## Pattern Notes

1. **Access directions** — `Rel_Access_w` for write access (producers → ingestion), `Rel_Access_r` for read access (consumers ← datasets)
2. **Data flow** — `Rel_Flow` shows data transformation pipeline: raw → curated → master data
3. **Data ownership** — `Business_Actor` (Data Steward) assigned to governance processes via `Rel_Assignment`
4. **Four zones** — Producers, Platform, Consumers, Governance form a clear data architecture layout
5. **Catalog serving** — `Rel_Serving` links the Data Catalog to curated datasets (metadata indexing)
6. **Mixed access patterns** — BI reads curated data, ML reads raw data, Reporting reads master data — showing different consumer needs
