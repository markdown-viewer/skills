# IAM & Authentication

User authentication flow with Cognito, IAM role assumption, and federated identity.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Users | `mxgraph.aws4.users` |
| Cognito | `mxgraph.aws4.cognito` |
| IAM | `mxgraph.aws4.identity_and_access_management` |
| STS | `mxgraph.aws4.sts` |
| AD Connector | `mxgraph.aws4.ad_connector` |
| API Gateway | `mxgraph.aws4.api_gateway` |
| Lambda | `mxgraph.aws4.lambda_function` |

## Example

Federated login with corporate AD, Cognito user pool, and IAM role-based access:

```plantuml
@startuml
left to right direction

rectangle "Users" {
  mxgraph.aws4.users "Employees" as emp
  mxgraph.aws4.users "Customers" as cust
}

rectangle "Identity Provider" {
  mxgraph.aws4.ad_connector "Corporate\nAD" as ad
  mxgraph.aws4.cognito "Cognito\nUser Pool" as cognito
}

rectangle "Authorization" {
  mxgraph.aws4.sts "STS" as sts
  mxgraph.aws4.identity_and_access_management "IAM\nRoles" as iam
}

rectangle "Protected API" {
  mxgraph.aws4.api_gateway "API\nGateway" as apigw
  mxgraph.aws4.lambda_function "Lambda" as fn
  mxgraph.aws4.dynamodb "DynamoDB" as db
}

emp --> ad : "SAML"
cust --> cognito : "OAuth2"
ad --> sts : "assume role"
cognito --> sts : "token exchange"
sts --> iam
iam --> apigw : "signed request"
apigw --> fn
fn --> db
@enduml
```

## Pattern Notes

1. **Dual identity sources**: employees via corporate AD (SAML), customers via Cognito (OAuth2/OIDC)
2. **STS role assumption**: both paths converge at STS to get temporary credentials scoped to IAM roles
3. **API Gateway authorizer**: validates JWT tokens or IAM signatures before forwarding to Lambda
4. **Least privilege**: each IAM role grants only the permissions needed for that user type

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| SSO | `mxgraph.aws4.single_sign_on` | Centralized workforce login |
| Directory Service | `mxgraph.aws4.directory_service` | Managed Active Directory |
| Verified Access | `mxgraph.aws4.verified_access` | Zero-trust app access |
| Verified Perms | `mxgraph.aws4.verified_permissions` | Fine-grained authorization |
| MFA Token | `mxgraph.aws4.mfa_token` | Multi-factor authentication |
| Cloud Directory | `mxgraph.aws4.cloud_directory` | Hierarchical identity store |
