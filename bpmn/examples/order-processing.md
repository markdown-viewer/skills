# Order Processing

E-commerce order fulfillment with payment validation, inventory check, parallel shipping and notification.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Start Event | `mxgraph.bpmn.event.start` |
| End Event | `mxgraph.bpmn.event.end` |
| Error End | `mxgraph.bpmn.event.errorEnd` |
| Exclusive Gateway | `mxgraph.bpmn.gateway2.exclusive` |
| Parallel Gateway | `mxgraph.bpmn.gateway2.parallel` |
| Timer Intermediate | `mxgraph.bpmn.event.timerCatching` |
| Data Object | `mxgraph.bpmn.data2.dataObject` |

## Example

Order received → validate payment → check inventory → parallel ship + notify → complete:

```plantuml
@startuml
left to right direction

mxgraph.bpmn.event.start "Order\nReceived" as start
rectangle "Validate\nPayment" as validate
mxgraph.bpmn.gateway2.exclusive "Payment\nOK?" as gw_pay
rectangle "Check\nInventory" as inv_check
mxgraph.bpmn.gateway2.exclusive "In\nStock?" as gw_stock
rectangle "Reserve\nItems" as reserve
mxgraph.bpmn.gateway2.parallel "Fork" as fork
rectangle "Ship\nOrder" as ship
rectangle "Send\nConfirmation" as notify
mxgraph.bpmn.gateway2.parallel "Join" as join
rectangle "Complete\nOrder" as complete
mxgraph.bpmn.event.end "Done" as end_ok

rectangle "Reject\nPayment" as reject_pay
mxgraph.bpmn.event.errorEnd "Payment\nFailed" as end_pay

rectangle "Backorder" as backorder
mxgraph.bpmn.event.timerCatching "Wait for\nRestock" as timer
rectangle "Retry\nInventory" as retry

start --> validate
validate --> gw_pay
gw_pay --> inv_check : "Valid"
gw_pay --> reject_pay : "Invalid"
reject_pay --> end_pay

inv_check --> gw_stock
gw_stock --> reserve : "Yes"
gw_stock --> backorder : "No"
backorder --> timer
timer --> retry
retry --> gw_stock

reserve --> fork
fork --> ship
fork --> notify
ship --> join
notify --> join
join --> complete
complete --> end_ok
@enduml
```

## Pattern Notes

1. **Exclusive Gateway (XOR)** — `mxgraph.bpmn.gateway2.exclusive` for conditional branches: payment valid/invalid, in stock/out of stock
2. **Parallel Gateway (AND)** — `mxgraph.bpmn.gateway2.parallel` for fork/join: ship and notify execute concurrently, both must complete before order completes
3. **Timer Intermediate** — `mxgraph.bpmn.event.timerCatching` represents a wait state (restock delay) before retrying inventory check
4. **Error End** — `mxgraph.bpmn.event.errorEnd` for exceptional termination (payment failure), distinct from normal End Event
5. **Retry loop** — backorder → timer → retry → gateway creates a loop pattern for stock replenishment

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| User Task | `mxgraph.bpmn.user_task` | Manual review/approval steps |
| Service Task | `mxgraph.bpmn.service_task` | Payment/inventory API calls |
| Message Start | `mxgraph.bpmn.event.messageStart` | Order submission trigger |
| Signal End | `mxgraph.bpmn.event.signalEnd` | Notify downstream systems |
| Inclusive Gateway | `mxgraph.bpmn.gateway2.inclusive` | Multiple simultaneous conditions |
| Data Input | `mxgraph.bpmn.data2.dataInput` | External data dependencies |
