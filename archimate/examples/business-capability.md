# Business Capability Model

Strategy and business capability mapping with value streams, resources, and courses of action.

## Key Elements

| Layer | Macros Used |
|-------|-------------|
| Strategy | `Strategy_Capability`, `Strategy_Resource`, `Strategy_CourseOfAction`, `Strategy_ValueStream` |
| Business | `Business_Service`, `Business_Process`, `Business_Actor` |

## Example

Retail company capability model: customer engagement, supply chain, and digital transformation strategy:

```plantuml
@startuml
!include <archimate/Archimate>

Strategy_ValueStream(vs, "Customer Value Stream")

rectangle "Core Capabilities" {
  Strategy_Capability(custEng, "Customer Engagement")
  Strategy_Capability(supplyChain, "Supply Chain Mgmt")
  Strategy_Capability(prodMgmt, "Product Management")
  Strategy_Capability(finance, "Financial Management")
}

rectangle "Customer Engagement" {
  Business_Service(marketing, "Marketing Service")
  Business_Service(sales, "Sales Service")
  Business_Service(support, "Customer Support")
  Business_Process(loyalty, "Loyalty Program")
}

rectangle "Supply Chain" {
  Business_Service(procurement, "Procurement")
  Business_Service(logistics, "Logistics")
  Business_Service(warehouse, "Warehousing")
}

rectangle "Digital Strategy" {
  Strategy_CourseOfAction(omni, "Omnichannel Strategy")
  Strategy_CourseOfAction(datadriven, "Data-Driven Decisions")
  Strategy_Resource(team, "Digital Team")
  Strategy_Resource(platform, "Cloud Platform")
}

Rel_Aggregation(vs, custEng, "")
Rel_Aggregation(vs, supplyChain, "")
Rel_Aggregation(vs, prodMgmt, "")
Rel_Aggregation(vs, finance, "")

Rel_Realization(marketing, custEng, "")
Rel_Realization(sales, custEng, "")
Rel_Realization(support, custEng, "")
Rel_Realization(loyalty, custEng, "")

Rel_Realization(procurement, supplyChain, "")
Rel_Realization(logistics, supplyChain, "")
Rel_Realization(warehouse, supplyChain, "")

Rel_Influence(omni, custEng, "enables")
Rel_Influence(datadriven, supplyChain, "optimizes")
Rel_Assignment(team, omni, "executes")
Rel_Assignment(platform, datadriven, "supports")
@enduml
```

## Pattern Notes

1. **Value Stream** — `Strategy_ValueStream` as the top-level container representing end-to-end customer value delivery
2. **Capability decomposition** — `Rel_Aggregation` breaks the value stream into core capabilities
3. **Business realization** — `Rel_Realization` links business services/processes to the capabilities they realize
4. **Strategy influence** — `Rel_Influence` shows how courses of action (strategies) affect capabilities
5. **Resource assignment** — `Rel_Assignment` links resources (team, platform) to the strategies they support
6. **Layered grouping** — Separate rectangles for core capabilities, sub-capabilities, and digital strategy initiatives
