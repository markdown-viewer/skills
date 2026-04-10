---
name: bpmn
description: Create business process and integration diagrams using PlantUML syntax with BPMN, EIP, and Lean Mapping stencil icons. Best for workflow automation, approval processes, message-based integration patterns, ETL pipelines, and value stream mapping. NOT for simple flowcharts (use mermaid) or UML activity diagrams (use uml skill).
metadata:
  author: BPMN diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://docu.md
---

# Business Process & Integration Diagram Generator

**Quick Start:** Choose diagram type → Declare stencil icons for events/gateways/tasks → Group into pools/lanes → Connect with arrow syntax → Wrap in ` ```plantuml ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```plantuml ` or ` ```puml ` code fence. NEVER use ` ```text ` — it will NOT render as a diagram.

## Critical Rules

- Every diagram starts with `@startuml` and ends with `@enduml`
- Use `left to right direction` for process flows (start→end reads left-to-right)
- Use `mxgraph.bpmn.*` for BPMN events, gateways, and task markers
- Use `mxgraph.eip.*` for Enterprise Integration Pattern icons
- Use `mxgraph.lean_mapping.*` for Value Stream Mapping symbols
- Default colors are applied automatically — you do NOT need to specify `fillColor` or `strokeColor`
- Use `rectangle "Pool" { ... }` for BPMN pools and lanes
- Sequence flows use `-->`, message flows use `..>` (dashed)

**Full stencil reference:** See [stencils/README.md](../uml/stencils/README.md) for 9500+ available icons.

## Mxgraph Stencil Syntax

```
mxgraph.<library>.<icon> "Label" as <alias>
```

### BPMN Stencil Family (`mxgraph.bpmn.*`)

**Events** — Circle shapes for process triggers and outcomes:

| Icon | Meaning |
|------|---------|
| `mxgraph.bpmn.event.start` | Start Event |
| `mxgraph.bpmn.event.end` | End Event |
| `mxgraph.bpmn.event.terminateEnd` | Terminate End |
| `mxgraph.bpmn.event.timerStart` | Timer Start |
| `mxgraph.bpmn.event.timerCatching` | Timer Intermediate |
| `mxgraph.bpmn.event.messageStart` | Message Start |
| `mxgraph.bpmn.event.messageCatching` | Message Catching |
| `mxgraph.bpmn.event.messageEnd` | Message End |
| `mxgraph.bpmn.event.errorEnd` | Error End |
| `mxgraph.bpmn.event.errorBound` | Error Boundary |
| `mxgraph.bpmn.event.signalStart` | Signal Start |
| `mxgraph.bpmn.event.signalEnd` | Signal End |

**Gateways** — Diamond shapes for branching/merging:

| Icon | Meaning |
|------|---------|
| `mxgraph.bpmn.gateway2.exclusive` | Exclusive Gateway (XOR) |
| `mxgraph.bpmn.gateway2.parallel` | Parallel Gateway (AND) |
| `mxgraph.bpmn.gateway2.inclusive` | Inclusive Gateway (OR) |
| `mxgraph.bpmn.gateway2.complex` | Complex Gateway |

**Tasks** — Use `rectangle` for tasks, stencil markers for typed tasks:

| Icon | Meaning |
|------|---------|
| `mxgraph.bpmn.user_task` | User Task |
| `mxgraph.bpmn.service_task` | Service Task |
| `mxgraph.bpmn.script_task` | Script Task |
| `mxgraph.bpmn.manual_task` | Manual Task |
| `mxgraph.bpmn.business_rule_task` | Business Rule Task |

**Data** — Document-like shapes:

| Icon | Meaning |
|------|---------|
| `mxgraph.bpmn.data2.dataObject` | Data Object |
| `mxgraph.bpmn.data2.dataInput` | Data Input |
| `mxgraph.bpmn.data2.dataOutput` | Data Output |

### EIP Stencil Family (`mxgraph.eip.*`)

| Icon | Meaning |
|------|---------|
| `mxgraph.eip.messageChannel` | Message Channel |
| `mxgraph.eip.deadLetterChannel` | Dead Letter Channel |
| `mxgraph.eip.content_based_router` | Content-Based Router |
| `mxgraph.eip.message_filter` | Message Filter |
| `mxgraph.eip.splitter` | Splitter |
| `mxgraph.eip.aggregator` | Aggregator |
| `mxgraph.eip.message_translator` | Message Translator |
| `mxgraph.eip.content_enricher` | Content Enricher |
| `mxgraph.eip.messaging_gateway` | Messaging Gateway |
| `mxgraph.eip.channel_adapter` | Channel Adapter |
| `mxgraph.eip.messaging_bridge` | Messaging Bridge |
| `mxgraph.eip.recipient_list` | Recipient List |
| `mxgraph.eip.wire_tap` | Wire Tap |
| `mxgraph.eip.event_driven_consumer` | Event-Driven Consumer |
| `mxgraph.eip.competing_consumers` | Competing Consumers |
| `mxgraph.eip.process_manager` | Process Manager |

### Lean Mapping Stencil Family (`mxgraph.lean_mapping.*`)

| Icon | Meaning |
|------|---------|
| `mxgraph.lean_mapping.outside_sources` | Supplier / Customer |
| `mxgraph.lean_mapping.manufacturing_process` | Process Step |
| `mxgraph.lean_mapping.supermarket` | Supermarket (Inventory Buffer) |
| `mxgraph.lean_mapping.fifo_lane` | FIFO Lane |
| `mxgraph.lean_mapping.production_kanban` | Production Kanban |
| `mxgraph.lean_mapping.withdrawal_kanban` | Withdrawal Kanban |
| `mxgraph.lean_mapping.signal_kanban` | Signal Kanban |
| `mxgraph.lean_mapping.truck_shipment` | Truck Shipment |
| `mxgraph.lean_mapping.operator` | Operator |
| `mxgraph.lean_mapping.inventory_box` | Inventory |
| `mxgraph.lean_mapping.kaizen_lightening_burst` | Kaizen Burst |
| `mxgraph.lean_mapping.mrp_erp` | MRP / ERP System |
| `mxgraph.lean_mapping.warehouse` | Warehouse |
| `mxgraph.lean_mapping.push_arrow` | Push Arrow |
| `mxgraph.lean_mapping.timeline2` | Timeline |

### Connection Types

| Syntax | Meaning | Use Case |
|--------|---------|----------|
| `A --> B` | Solid arrow | Sequence flow (task→task) |
| `A ..> B` | Dashed arrow | Message flow (cross-pool) / async trigger |
| `A --> B : "label"` | Labeled solid | Conditional flow (gateway branch) |
| `A ..> B : "label"` | Labeled dashed | Named message / signal |

### Quick Example

```plantuml
@startuml
left to right direction

mxgraph.bpmn.event.start "Start" as start
rectangle "Review\nRequest" as review
mxgraph.bpmn.gateway2.exclusive "Approved?" as gw
rectangle "Process\nOrder" as process
rectangle "Notify\nRejection" as reject
mxgraph.bpmn.event.end "End" as end_ok
mxgraph.bpmn.event.end "End" as end_fail

start --> review
review --> gw
gw --> process : "Yes"
gw --> reject : "No"
process --> end_ok
reject --> end_fail
@enduml
```

## Diagram Types

| Type | Purpose | Key Stencils | Example |
|------|---------|--------------|---------|
| Order Processing | E-commerce / fulfillment | `mxgraph.bpmn.event.*`, `mxgraph.bpmn.gateway2.*` | [order-processing.md](examples/order-processing.md) |
| Approval Workflow | Multi-level approval | `mxgraph.bpmn.event.*`, `mxgraph.bpmn.gateway2.*` | [approval-workflow.md](examples/approval-workflow.md) |
| EIP Messaging | Message routing & transformation | `mxgraph.eip.*` | [eip-messaging.md](examples/eip-messaging.md) |
| ETL Pipeline | Data extraction & loading | `mxgraph.bpmn.event.*`, `mxgraph.eip.*` | [etl-pipeline.md](examples/etl-pipeline.md) |
| Value Stream | Lean manufacturing flow | `mxgraph.lean_mapping.*` | [value-stream.md](examples/value-stream.md) |
| Microservice Orchestration | Service choreography | `mxgraph.bpmn.event.*`, `mxgraph.eip.*` | [microservice-orchestration.md](examples/microservice-orchestration.md) |
| Event-Driven Architecture | Pub/Sub event flows | `mxgraph.bpmn.event.*`, `mxgraph.eip.*` | [event-driven.md](examples/event-driven.md) |
| Customer Service | Support ticket lifecycle | `mxgraph.bpmn.event.*`, `mxgraph.bpmn.gateway2.*` | [customer-service.md](examples/customer-service.md) |
