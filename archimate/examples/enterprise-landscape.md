# Enterprise Landscape

Full three-layer ArchiMate view: Business → Application → Technology for an insurance company.

## Key Elements

| Layer | Macros Used |
|-------|-------------|
| Business | `Business_Actor`, `Business_Process`, `Business_Service` |
| Application | `Application_Component`, `Application_Service` |
| Technology | `Technology_Node`, `Technology_Device`, `Technology_CommunicationNetwork` |

## Example

Insurance claim handling across business processes, application services, and infrastructure:

```plantuml
@startuml
!include <archimate/Archimate>

rectangle "Business Layer" {
  Business_Actor(customer, "Customer")
  Business_Actor(agent, "Claims Agent")
  Business_Process(submit, "Submit Claim")
  Business_Process(assess, "Assess Claim")
  Business_Process(pay, "Process Payment")
  Business_Service(claimSvc, "Claims Service")
  Business_Service(paySvc, "Payment Service")
}

rectangle "Application Layer" {
  Application_Component(claimApp, "Claims System")
  Application_Component(crmApp, "CRM System")
  Application_Component(finApp, "Finance System")
  Application_Service(claimAPI, "Claims API")
  Application_Service(custAPI, "Customer API")
  Application_Service(payAPI, "Payment API")
  Application_DataObject(claimData, "Claim Record")
  Application_DataObject(custData, "Customer Profile")
}

rectangle "Technology Layer" {
  Technology_Node(appSrv, "Application Server")
  Technology_Node(webSrv, "Web Server")
  Technology_Device(dbSrv, "Database Server")
  Technology_CommunicationNetwork(lan, "Corporate LAN")
}

Rel_Triggering(customer, submit, "files claim")
Rel_Assignment(agent, assess, "investigates")
Rel_Triggering(submit, assess, "")
Rel_Triggering(assess, pay, "")
Rel_Realization(submit, claimSvc, "")
Rel_Realization(pay, paySvc, "")

Rel_Serving(claimAPI, claimSvc, "")
Rel_Serving(custAPI, claimSvc, "")
Rel_Serving(payAPI, paySvc, "")
Rel_Realization(claimApp, claimAPI, "")
Rel_Realization(crmApp, custAPI, "")
Rel_Realization(finApp, payAPI, "")
Rel_Access(claimApp, claimData, "")
Rel_Access(crmApp, custData, "")

Rel_Assignment(appSrv, claimApp, "")
Rel_Assignment(appSrv, finApp, "")
Rel_Assignment(webSrv, crmApp, "")
Rel_Serving(dbSrv, appSrv, "")
Rel_Association(lan, appSrv, "")
Rel_Association(lan, webSrv, "")
Rel_Association(lan, dbSrv, "")
@enduml
```

## Pattern Notes

1. **Three-layer structure** — `rectangle "Business Layer"`, `"Application Layer"`, `"Technology Layer"` map to core ArchiMate layers
2. **Realization** — `Rel_Realization` links business processes to services, and application components to application services
3. **Serving** — `Rel_Serving` shows application services serving business services (upward dependency)
4. **Assignment** — `Rel_Assignment` assigns technology nodes to application components (hosting relationship)
5. **Triggering chain** — `Rel_Triggering` creates the sequential flow: Submit → Assess → Pay
6. **Data objects** — `Application_DataObject` with `Rel_Access` shows which components read/write which data
