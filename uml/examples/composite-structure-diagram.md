# Composite Structure Diagram

Shows the internal structure of a classifier and collaborations between parts.

## Key Elements

| Element | Syntax | Description |
|---|---|---|
| Class with parts | `component "Name" { }` | Container showing internal structure |
| Part | `component "name : Type"` | Named part inside a classifier |
| Port | `portin` / `portout` | Interaction point on boundary |
| Connector | `part1 --> part2` | Link between internal parts |
| Collaboration | Use note/package for collaboration | Dashed ellipse (approximate) |
| Role | Elements inside collaboration | Participants in collaboration |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Classifier | `#dae8fc` (light blue) | Main class container |
| Part | `#d5e8d4` (light green) | Internal parts |
| Port | `#fff2cc` (light yellow) | Interaction points |
| Connector | `#333333` (dark gray) | Internal connections |
| Collaboration | `#e1d5e7` (light purple) | Collaboration containers |

## Example 1

Server component showing internal structure with ports and parts:

```plantuml
@startuml
skinparam component {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
}

package "WebServer" #dae8fc {
  component "requestHandler : RequestHandler" as rh #d5e8d4
  component "authModule : AuthModule" as auth #d5e8d4
  component "router : Router" as router #d5e8d4
  component "cache : CacheManager" as cache #fff2cc
  component "logger : Logger" as logger #e1d5e7

  portin "HTTP In" as httpIn
  portout "DB Out" as dbOut

  httpIn --> rh
  rh --> auth : authenticate
  rh --> router : route
  router --> cache : lookup
  router --> dbOut : query
  rh --> logger : log
  auth --> logger : log
}

package "Collaboration: RequestProcessing" #e1d5e7 {
  component ":Handler" as ch #f8cecc
  component ":Validator" as cv #f8cecc
  component ":Processor" as cp #f8cecc

  ch --> cv : validate
  cv --> cp : process
}

note right of "WebServer"
  Internal structure shows
  how parts collaborate
  to handle requests
end note
@enduml
```
