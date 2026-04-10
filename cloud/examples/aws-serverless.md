# AWS Serverless Architecture

Event-driven serverless architecture with API Gateway, Lambda, DynamoDB, and S3.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Client App | `mxgraph.aws4.mobile_client` |
| Cognito | `mxgraph.aws4.cognito` |
| API Gateway | `mxgraph.aws4.api_gateway` |
| Lambda | `mxgraph.aws4.lambda` |
| DynamoDB | `mxgraph.aws4.dynamodb` |
| S3 | `mxgraph.aws4.s3` |
| SQS | `mxgraph.aws4.sqs` |
| SNS | `mxgraph.aws4.sns` |
| EventBridge | `mxgraph.aws4.eventbridge` |
| Step Functions | `mxgraph.aws4.step_functions` |
| CloudWatch | `mxgraph.aws4.cloudwatch` |

## Example

```plantuml
@startuml
left to right direction

mxgraph.aws4.mobile_client "Client App" as client

rectangle "AWS Region" {
  mxgraph.aws4.cognito "Cognito" as cognito
  mxgraph.aws4.api_gateway "API Gateway" as apigw
  mxgraph.aws4.lambda "Lambda\n(API Handler)" as lambda_api
  mxgraph.aws4.dynamodb "DynamoDB" as dynamodb
  mxgraph.aws4.s3 "S3\n(Uploads)" as s3
  mxgraph.aws4.lambda "Lambda\n(S3 Trigger)" as lambda_s3
  mxgraph.aws4.sqs "SQS Queue" as sqs
  mxgraph.aws4.lambda "Lambda\n(Worker)" as lambda_worker
  mxgraph.aws4.sns "SNS Topic" as sns
  mxgraph.aws4.eventbridge "EventBridge" as eventbridge
  mxgraph.aws4.step_functions "Step Functions" as stepfn
  mxgraph.aws4.cloudwatch "CloudWatch" as cw
}

' Sync API path
client --> cognito : auth
client --> apigw
apigw --> lambda_api
lambda_api --> dynamodb

' Upload & async processing path
client --> s3 : upload
s3 ..> lambda_s3 : trigger
lambda_s3 --> sqs
sqs ..> lambda_worker : poll
lambda_worker --> sns

' Event fan-out
dynamodb ..> sns : streams
sns --> eventbridge
eventbridge ..> stepfn : rule
@enduml
```

## Pattern Notes

1. **Flat layout**: Serverless uses Region container only — no VPC/subnet needed
2. **Dashed = async**: `..>` for event-driven triggers (S3, SQS polling, DynamoDB Streams), `-->` for sync calls
3. **External clients**: Place `client` outside the Region rectangle
4. **Two processing paths**: Sync API path (top) and async upload/processing path (bottom) share SNS fan-out

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| AppSync | `mxgraph.aws4.appsync` | GraphQL API alternative |
| Firehose | `mxgraph.aws4.kinesis_data_firehose` | Streaming delivery to S3 |
| X-Ray | `mxgraph.aws4.xray` | Distributed tracing |
| Secrets Manager | `mxgraph.aws4.secrets_manager` | Lambda secrets injection |
| DynamoDB Stream | `mxgraph.aws4.dynamodb_stream` | Change data capture trigger |
| SES | `mxgraph.aws4.simple_email_service` | Email notification sending |
