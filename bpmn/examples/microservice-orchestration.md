# Microservice Orchestration

Saga orchestrator pattern: order service coordinates payment, inventory, and shipping services with compensation on failure.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Start Event | `mxgraph.bpmn.event.start` |
| End Event | `mxgraph.bpmn.event.end` |
| Error Boundary | `mxgraph.bpmn.event.errorBound` |
| Error End | `mxgraph.bpmn.event.errorEnd` |
| Exclusive Gateway | `mxgraph.bpmn.gateway2.exclusive` |
| Service Task | `mxgraph.bpmn.service_task` |
| Messaging Gateway | `mxgraph.eip.messaging_gateway` |
| Message Channel | `mxgraph.eip.messageChannel` |
| Dead Letter Channel | `mxgraph.eip.deadLetterChannel` |

## Example

Order saga: reserve → charge → ship, with compensating transactions on failure:

```plantuml
@startuml
left to right direction

mxgraph.bpmn.event.start "Order\nCreated" as start

rectangle "Orchestrator" {
  mxgraph.eip.messaging_gateway "Saga\nCoordinator" as saga
  mxgraph.bpmn.gateway2.exclusive "All\nSuccess?" as gw_result
}

rectangle "Inventory Service" {
  mxgraph.bpmn.service_task "Reserve\nStock" as reserve
  mxgraph.bpmn.service_task "Release\nStock" as release
}

rectangle "Payment Service" {
  mxgraph.bpmn.service_task "Charge\nPayment" as charge
  mxgraph.bpmn.service_task "Refund\nPayment" as refund
}

rectangle "Shipping Service" {
  mxgraph.bpmn.service_task "Create\nShipment" as ship
  mxgraph.bpmn.service_task "Cancel\nShipment" as cancel_ship
}

mxgraph.eip.messageChannel "Command\nBus" as cmd_bus
mxgraph.eip.messageChannel "Reply\nBus" as reply_bus
mxgraph.eip.deadLetterChannel "Failed\nSagas" as dlq

mxgraph.bpmn.event.end "Order\nCompleted" as end_ok
mxgraph.bpmn.event.errorEnd "Order\nFailed" as end_fail

start --> saga
saga --> cmd_bus
cmd_bus --> reserve
cmd_bus --> charge
cmd_bus --> ship
reserve ..> reply_bus
charge ..> reply_bus
ship ..> reply_bus
reply_bus --> gw_result

gw_result --> end_ok : "Success"
gw_result --> release : "Fail"
release --> refund
refund --> cancel_ship
cancel_ship --> dlq
dlq --> end_fail
@enduml
```

## Pattern Notes

1. **Saga Coordinator** — `mxgraph.eip.messaging_gateway` acts as the central orchestrator, sending commands to services via Command Bus and receiving replies
2. **Service containers** — Each microservice is a `rectangle` pool containing its forward action and compensating action (reserve/release, charge/refund, create/cancel)
3. **Command/Reply buses** — `mxgraph.eip.messageChannel` separates command flow (solid `-->`) from reply flow (dashed `..>` for async responses)
4. **Compensation chain** — On failure, the gateway triggers compensating transactions in reverse order: release stock → refund payment → cancel shipment
5. **Dead Letter Channel** — Failed sagas land in `mxgraph.eip.deadLetterChannel` for manual investigation
6. **BPMN + EIP hybrid** — Service Tasks (`mxgraph.bpmn.service_task`) represent microservice calls; EIP patterns handle the messaging infrastructure

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Process Manager | `mxgraph.eip.process_manager` | Long-running process coordination |
| Routing Slip | `mxgraph.eip.routing_slip` | Dynamic service invocation chain |
| Transactional Client | `mxgraph.eip.transactional_client` | Transaction-aware messaging |
| Timer Catching | `mxgraph.bpmn.event.timerCatching` | Saga timeout handling |
| Compensation | `mxgraph.bpmn.compensation` | Undo/rollback visual marker |
| Smart Proxy | `mxgraph.eip.smart_proxy` | Return address tracking |
