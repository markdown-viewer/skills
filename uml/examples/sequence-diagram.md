# Sequence Diagram

Shows message interactions between objects in chronological order.

## Key Elements

- **Participant**: `participant "Name" as alias` — rectangle lifeline
- **Actor**: `actor "Name" as alias` — stick figure lifeline
- **Entity**: `entity "Name" as alias` — circle with underline
- **Database**: `database "Name" as alias` — cylinder lifeline
- **Activation**: `activate` / `deactivate` or `++` / `--` shorthand
- **Destroy**: `destroy participant` — X mark on lifeline
- **Frame**: `box "Label" #color ... end box` — group participants

## Message Types

| Message | Syntax | Description |
|---|---|---|
| Synchronous | `->` | Solid line, filled arrow |
| Asynchronous | `->>` | Solid line, open arrow |
| Return | `-->` | Dashed line |
| Create | `create participant` + `->` | Creates new object |
| Self-call | `A -> A` | Message to self |

## Combined Fragments

| Fragment | Syntax | Description |
|---|---|---|
| alt/else | `alt ... else ... end` | Alternative (if-else) |
| opt | `opt ... end` | Optional (if) |
| loop | `loop ... end` | Loop iteration |
| par | `par ... else ... end` | Parallel execution |
| break | `break ... end` | Break out |

## Recommended Colors

| Element | Color | Usage |
|---|---|---|
| Actor | default | User/external entity |
| Frontend | `#96CBFE` (sky blue) | UI components |
| Backend | `#A8D08D` (sage green) | Server/service |
| Database | `#F4B183` (peach) | Data storage |
| External | `#D5A6E6` (lavender) | Third-party services |
| Box group | `#F5F5F5` (light gray) | Participant grouping |

## Example 1

E-commerce order processing with multiple participants and fragments:

```plantuml
@startuml
skinparam participant {
  BackgroundColor #dae8fc
  BorderColor #6c8ebf
  FontName Arial
}
skinparam sequence {
  ArrowColor #333333
  LifeLineBorderColor #999999
  GroupBackgroundColor #f5f5f5
  GroupBorderColor #cccccc
  DividerBackgroundColor #eeeeee
}
skinparam database {
  BackgroundColor #fff2cc
  BorderColor #d6b656
}

actor "Customer" as customer
box "Frontend" #F5F5F5
  participant "Web Store" as web #96CBFE
end box
box "Backend Services" #F5F5F5
  participant "Order Service" as order #A8D08D
  participant "Payment Service" as payment #A8D08D
  participant "Inventory" as inv #A8D08D
end box
database "Orders DB" as db #F4B183
participant "Email Service" as email #D5A6E6

== Place Order ==

customer -> web : Browse & Add to Cart
activate web
web -> order : POST /orders
activate order

order -> inv : Check stock
activate inv
inv --> order : Stock confirmed
deactivate inv

order -> db : Create order (PENDING)
activate db
db --> order : Order #12345
deactivate db

order --> web : Order created
deactivate order

web --> customer : Show order summary
deactivate web

== Process Payment ==

customer -> web : Submit payment
activate web
web -> payment : POST /payments
activate payment

alt Payment Success
  payment -> order : Payment confirmed
  activate order
  order -> db : Update order (PAID)
  order -> email : Send confirmation
  activate email
  email --> customer : Order confirmation email
  deactivate email
  order --> payment : ACK
  deactivate order
  payment --> web : Payment OK
else Payment Failed
  payment --> web : Payment declined
  web --> customer : Show error, retry
end

deactivate payment
deactivate web
@enduml
```

## Example 2

AWS serverless API flow using stdlib icons (`<$SpriteName>` in participant labels):

```plantuml
@startuml
' awslib sequence diagram: embed sprites in participant labels with <$SpriteName>
!include <awslib/AWSCommon>
!include <awslib/AWSSimplified.puml>
!include <awslib/Compute/Lambda>
!include <awslib/ApplicationIntegration/APIGateway>
!include <awslib/ApplicationIntegration/SimpleQueueService>
!include <awslib/Database/DynamoDB>
!include <awslib/Storage/SimpleStorageService>
!include <awslib/general/Client>

skinparam BoxPadding 10
hide footbox

actor "<$Client>\nMobile App" as client

box "AWS API Layer" #LightBlue
  participant "<$APIGateway>\nAPI Gateway" as apigw
end box

box "Compute" #LightGreen
  participant "<$Lambda>\nAuth" as authLambda
  participant "<$Lambda>\nProcess" as procLambda
end box

box "Data" #LightYellow
  participant "<$DynamoDB>\nDynamoDB" as dynamo
  participant "<$SimpleStorageService>\nS3" as s3
  participant "<$SimpleQueueService>\nSQS" as sqs
end box

client -> apigw : POST /process
activate apigw

apigw -> authLambda : Verify token
activate authLambda
authLambda --> apigw : 200 OK
deactivate authLambda

apigw -> procLambda : Process request
activate procLambda
procLambda -> dynamo : Save record
procLambda -> sqs : Enqueue task
procLambda -> s3 : Upload file
procLambda --> apigw : 202 Accepted
deactivate procLambda

apigw --> client : 202 Accepted
deactivate apigw
@enduml
```
