# Application Integration

Application-to-application integration view showing data flows, interfaces, and shared services.

## Key Elements

| Layer | Macros Used |
|-------|-------------|
| Application | `Application_Component`, `Application_Service`, `Application_Interface`, `Application_DataObject` |
| Technology | `Technology_Service` |

## Example

E-commerce platform integration: web portal, order management, inventory, payment, and shipping systems:

```plantuml
@startuml
!include <archimate/Archimate>

Application_Interface(webUI, "Web Portal UI")

rectangle "Core Applications" {
  Application_Component(orderMgmt, "Order Management")
  Application_Component(inventory, "Inventory System")
  Application_Component(payment, "Payment Gateway")
  Application_Component(shipping, "Shipping Service")
  Application_Component(crm, "CRM")
}

rectangle "Integration Layer" {
  Application_Service(orderAPI, "Order API")
  Application_Service(stockAPI, "Stock API")
  Application_Service(payAPI, "Payment API")
  Application_Service(shipAPI, "Shipping API")
  Application_Service(custAPI, "Customer API")
  Technology_Service(esb, "Enterprise Service Bus")
}

rectangle "Data Stores" {
  Application_DataObject(orderDB, "Order Data")
  Application_DataObject(stockDB, "Inventory Data")
  Application_DataObject(custDB, "Customer Data")
}

Rel_Serving(orderAPI, webUI, "")
Rel_Realization(orderMgmt, orderAPI, "")
Rel_Realization(inventory, stockAPI, "")
Rel_Realization(payment, payAPI, "")
Rel_Realization(shipping, shipAPI, "")
Rel_Realization(crm, custAPI, "")

Rel_Serving(esb, orderAPI, "routes")
Rel_Serving(esb, stockAPI, "routes")
Rel_Serving(esb, payAPI, "routes")
Rel_Serving(esb, shipAPI, "routes")
Rel_Serving(esb, custAPI, "routes")

Rel_Flow(orderMgmt, inventory, "check stock")
Rel_Flow(orderMgmt, payment, "charge")
Rel_Flow(orderMgmt, shipping, "dispatch")
Rel_Flow(crm, orderMgmt, "customer context")

Rel_Access(orderMgmt, orderDB, "")
Rel_Access(inventory, stockDB, "")
Rel_Access(crm, custDB, "")
@enduml
```

## Pattern Notes

1. **Application Interface** — `Application_Interface` for the user-facing entry point (Web Portal UI)
2. **Realization** — Each `Application_Component` realizes its corresponding `Application_Service` (API)
3. **ESB pattern** — `Technology_Service` represents the Enterprise Service Bus routing all API traffic
4. **Flow** — `Rel_Flow` shows data/message flows between applications (check stock, charge, dispatch)
5. **Access** — `Rel_Access` links components to their data stores
6. **Serving** — `Rel_Serving` shows APIs serving the UI and ESB serving all APIs
