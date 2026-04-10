# AWS Basic Architecture

Three-tier web application with CloudFront, ALB, EC2 Auto Scaling, and RDS in a VPC.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Users | `mxgraph.aws4.users` |
| CloudFront | `mxgraph.aws4.cloudfront` |
| S3 | `mxgraph.aws4.s3` |
| ALB | `mxgraph.aws4.application_load_balancer` |
| NAT Gateway | `mxgraph.aws4.nat_gateway` |
| EC2 | `mxgraph.aws4.ec2` |
| RDS | `mxgraph.aws4.rds` |

## Example

Three-tier architecture with multi-AZ VPC:

```plantuml
@startuml
left to right direction
mxgraph.aws4.users "Users" as users
mxgraph.aws4.cloudfront "CloudFront" as cf
mxgraph.aws4.s3 "S3\n(Static Assets)" as s3

cloud "AWS Cloud" {
  rectangle "VPC" {
    rectangle "Public Subnet (AZ-1)" {
      mxgraph.aws4.application_load_balancer "ALB" as alb
    }
    rectangle "Public Subnet (AZ-2)" {
      mxgraph.aws4.nat_gateway "NAT\nGateway" as nat
    }
    rectangle "Private Subnet (AZ-1)" {
      mxgraph.aws4.ec2 "EC2" as ec2a
      mxgraph.aws4.ec2 "EC2" as ec2b
    }
    rectangle "Private Subnet (AZ-2)" {
      mxgraph.aws4.rds "RDS\n(Primary)" as rds1
      mxgraph.aws4.rds "RDS\n(Standby)" as rds2
    }
  }
}

users --> cf
cf --> s3
cf --> alb
alb --> ec2a
alb --> ec2b
ec2a --> rds1
rds1 ..> rds2 : replication
@enduml
```

## Pattern Notes

1. **`left to right direction`** — cloud architectures flow left-to-right: Users → Edge → Compute → Data
2. **Nested containers**: `cloud "AWS Cloud"` → `rectangle "VPC"` → `rectangle "Subnet"` maps to AWS resource hierarchy
3. **Multi-AZ**: duplicate subnets and services across availability zones for high availability
4. **Dashed for replication**: `rds1 ..> rds2` shows async standby replication

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Auto Scaling | `mxgraph.aws4.auto_scaling2` | EC2 scaling group boundary |
| WAF | `mxgraph.aws4.waf` | Web application firewall at ALB |
| ElastiCache | `mxgraph.aws4.elasticache` | In-memory caching layer |
| Route 53 | `mxgraph.aws4.route_53` | DNS routing to CloudFront |
| Certificate Mgr | `mxgraph.aws4.certificate_manager` | TLS certificate provisioning |
| Internet Gateway | `mxgraph.aws4.internet_gateway` | VPC internet entry point |
