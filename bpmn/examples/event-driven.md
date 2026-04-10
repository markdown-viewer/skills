# Event-Driven Architecture

Event sourcing with domain events published to topics, consumed by multiple subscribers with filtering and replay.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Signal Start | `mxgraph.bpmn.event.signalStart` |
| Signal End | `mxgraph.bpmn.event.signalEnd` |
| Message Catching | `mxgraph.bpmn.event.messageCatching` |
| End Event | `mxgraph.bpmn.event.end` |
| Event-Driven Consumer | `mxgraph.eip.event_driven_consumer` |
| Competing Consumers | `mxgraph.eip.competing_consumers` |
| Content-Based Router | `mxgraph.eip.content_based_router` |
| Durable Subscriber | `mxgraph.eip.durable_subscriber` |
| Message Channel | `mxgraph.eip.messageChannel` |
| Message Filter | `mxgraph.eip.message_filter` |
| Channel Adapter | `mxgraph.eip.channel_adapter` |

## Example

Domain events from Order and User services published to event bus, consumed by analytics, notification, and search services:

```plantuml
@startuml
left to right direction

rectangle "Event Producers" {
  mxgraph.bpmn.event.signalEnd "Order\nEvents" as evt_order
  mxgraph.bpmn.event.signalEnd "User\nEvents" as evt_user
  mxgraph.bpmn.event.signalEnd "Payment\nEvents" as evt_pay
}

mxgraph.eip.messageChannel "Event\nBus" as bus

mxgraph.eip.content_based_router "Event\nRouter" as router

rectangle "Analytics Pipeline" {
  mxgraph.eip.durable_subscriber "Analytics\nSubscriber" as analytics_sub
  mxgraph.eip.channel_adapter "Data\nWarehouse" as dw
}

rectangle "Notification Service" {
  mxgraph.eip.message_filter "Filter\nHigh-Priority" as notif_filter
  mxgraph.eip.competing_consumers "Notification\nWorkers" as notif_workers
  mxgraph.eip.channel_adapter "Email /\nSMS / Push" as send
}

rectangle "Search Index" {
  mxgraph.eip.event_driven_consumer "Search\nConsumer" as search_consumer
  mxgraph.eip.channel_adapter "Elasticsearch" as es
}

rectangle "Event Store" {
  mxgraph.eip.channel_adapter "Append to\nEvent Log" as event_log
  mxgraph.bpmn.event.messageCatching "Replay\nRequest" as replay
}

evt_order --> bus
evt_user --> bus
evt_pay --> bus
bus --> router
bus --> event_log

router --> analytics_sub : "all events"
router --> notif_filter : "order + payment"
router --> search_consumer : "order + user"

analytics_sub --> dw
notif_filter --> notif_workers
notif_workers --> send
search_consumer --> es

replay ..> bus : "replay events"
@enduml
```

## Pattern Notes

1. **Signal Events** — `mxgraph.bpmn.event.signalEnd` represents domain events being emitted (broadcast signals); `mxgraph.bpmn.event.signalStart` for event triggers
2. **Content-Based Router** — Routes events to different consumers based on event type (order events go to all, payment only to notifications)
3. **Durable Subscriber** — `mxgraph.eip.durable_subscriber` for analytics ensures no events are lost even if the consumer is temporarily offline
4. **Competing Consumers** — `mxgraph.eip.competing_consumers` for notification workers allows horizontal scaling with load balancing
5. **Event-Driven Consumer** — `mxgraph.eip.event_driven_consumer` for search reacts to events as they arrive (push model)
6. **Event Store + Replay** — Event log persists all events; `mxgraph.bpmn.event.messageCatching` with dashed arrow shows replay capability
7. **Message Filter** — `mxgraph.eip.message_filter` drops low-priority events before they reach notification workers

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Polling Consumer | `mxgraph.eip.polling_consumer` | Batch event consumption |
| Selective Consumer | `mxgraph.eip.selective_consumer` | Filter events at consumer |
| Message Dispatcher | `mxgraph.eip.message_dispatcher` | Route to specific handlers |
| Message Store | `mxgraph.eip.message_store` | Event persistence/replay |
| Service Activator | `mxgraph.eip.service_activator` | Invoke service on event arrival |
| Wire Tap | `mxgraph.eip.wire_tap` | Debugging/audit event copy |
