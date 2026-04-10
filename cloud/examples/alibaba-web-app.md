# Alibaba Cloud Web Application Architecture

Three-tier web application with CDN, WAF, SLB, ECS, PolarDB, and Redis.

## Key Elements

| Component | Stencil |
|-----------|---------|
| User | `mxgraph.alibaba_cloud.user` |
| DNS | `mxgraph.alibaba_cloud.dns_domain_name_system` |
| CDN | `mxgraph.alibaba_cloud.cdn_content_distribution_network` |
| WAF | `mxgraph.alibaba_cloud.waf_web_application_firewall` |
| SLB | `mxgraph.alibaba_cloud.slb_server_load_balancer_01` |
| ECS | `mxgraph.alibaba_cloud.ecs_elastic_compute_service` |
| PolarDB | `mxgraph.alibaba_cloud.polardb` |
| Redis | `mxgraph.alibaba_cloud.redis_kvstore` |
| OSS | `mxgraph.alibaba_cloud.oss_object_storage_service` |
| NAT Gateway | `mxgraph.alibaba_cloud.nat_gateway` |

## Example

```plantuml
@startuml
left to right direction

mxgraph.alibaba_cloud.user "Users" as users

cloud "Alibaba Cloud" {
  mxgraph.alibaba_cloud.dns_domain_name_system "Cloud DNS" as dns
  mxgraph.alibaba_cloud.cdn_content_distribution_network "CDN" as cdn
  mxgraph.alibaba_cloud.waf_web_application_firewall "WAF" as waf
  mxgraph.alibaba_cloud.oss_object_storage_service "OSS\n(Static Assets)" as oss

  rectangle "VPC (10.0.0.0/16)" {
    rectangle "Public Zone" {
      mxgraph.alibaba_cloud.slb_server_load_balancer_01 "SLB" as slb
      mxgraph.alibaba_cloud.nat_gateway "NAT Gateway" as nat
    }

    rectangle "Private Zone (AZ-A)" {
      mxgraph.alibaba_cloud.ecs_elastic_compute_service "ECS-1" as ecs1
      mxgraph.alibaba_cloud.ecs_elastic_compute_service "ECS-2" as ecs2
      mxgraph.alibaba_cloud.polardb "PolarDB\n(Primary)" as polardb1
    }

    rectangle "Private Zone (AZ-B)" {
      mxgraph.alibaba_cloud.ecs_elastic_compute_service "ECS-3" as ecs3
      mxgraph.alibaba_cloud.ecs_elastic_compute_service "ECS-4" as ecs4
      mxgraph.alibaba_cloud.redis_kvstore "Redis (Cache)" as redis
      mxgraph.alibaba_cloud.polardb "PolarDB\n(Read-Only)" as polardb2
    }
  }
}

' Edge services
users --> dns
dns --> cdn
cdn --> oss : static
cdn --> waf : dynamic
waf --> slb

' Load balancing to compute
slb --> ecs1
slb --> ecs3

' App to data
ecs1 --> polardb1
ecs2 --> polardb1
ecs3 --> redis
ecs4 --> redis

' Replication
polardb1 ..> polardb2 : replication
@enduml
```

## Pattern Notes

1. **Direct shape pattern**: `mxgraph.alibaba_cloud.<name>` — no `resourceIcon` prefix needed
2. **Multi-AZ**: ECS across two private zones, SLB distributes cross-AZ traffic
3. **Edge services chain**: Users → DNS → CDN → WAF → SLB (left-to-right flow)
4. **Dashed replication**: `..>` for PolarDB primary-to-read-only replication

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| DDoS Protection | `mxgraph.alibaba_cloud.ddos_protection` | DDoS mitigation |
| Log Service | `mxgraph.alibaba_cloud.sls_simple_log_service` | Centralized logging |
| Auto Scaling | `mxgraph.alibaba_cloud.ess_elastic_scaling_service` | ECS auto scaling |
| Cloud Monitor | `mxgraph.alibaba_cloud.cms_cloud_monitor_service` | Health monitoring |
| RAM | `mxgraph.alibaba_cloud.ram_resource_access_management` | Access control |
| API Gateway | `mxgraph.alibaba_cloud.apigateway` | API management |
