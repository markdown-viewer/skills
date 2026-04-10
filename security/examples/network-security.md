# Network Security

Defense-in-depth network architecture with firewall layers, DDoS protection, and security groups.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Shield | `mxgraph.aws4.shield` |
| WAF | `mxgraph.aws4.generic_firewall` |
| Network Firewall | `mxgraph.aws4.network_firewall` |
| Firewall Manager | `mxgraph.aws4.firewall_manager` |
| Security Group | `mxgraph.aws4.security_group` |
| CloudFront | `mxgraph.aws4.cloudfront` |
| ALB | `mxgraph.aws4.application_load_balancer` |
| EC2 | `mxgraph.aws4.ec2` |

## Example

Multi-layer perimeter defense from edge to instance level:

```plantuml
@startuml
left to right direction

mxgraph.aws4.users "Internet\nTraffic" as inet

rectangle "Edge Protection" {
  mxgraph.aws4.shield "Shield\nAdvanced" as shield
  mxgraph.aws4.generic_firewall "WAF\nRules" as waf
  mxgraph.aws4.cloudfront "CloudFront" as cf
}

rectangle "VPC Perimeter" {
  mxgraph.aws4.network_firewall "Network\nFirewall" as nfw
  mxgraph.aws4.application_load_balancer "ALB" as alb
}

rectangle "Instance Security" {
  mxgraph.aws4.security_group "Security\nGroup" as sg
  mxgraph.aws4.ec2 "App\nServer" as ec2
  mxgraph.aws4.ec2 "App\nServer" as ec2b
}

mxgraph.aws4.firewall_manager "Firewall\nManager" as fmgr

inet --> shield
shield --> waf
waf --> cf
cf --> nfw
nfw --> alb
alb --> sg
sg --> ec2
sg --> ec2b
fmgr ..> waf : "manage"
fmgr ..> nfw : "manage"
@enduml
```

## Pattern Notes

1. **Defense-in-depth**: Shield (L3/L4 DDoS) → WAF (L7 rules) → Network Firewall (stateful inspection) → Security Groups (instance)
2. **Shield Advanced**: automatic DDoS mitigation with real-time metrics and cost protection
3. **WAF rules**: rate limiting, geo-blocking, SQL injection / XSS protection at CloudFront edge
4. **Firewall Manager**: centrally manages WAF and Network Firewall policies across multiple accounts

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| WAF | `mxgraph.aws4.waf` | Web application firewall icon |
| WAF Bot Control | `mxgraph.aws4.waf_bot_control` | Bot mitigation rules |
| WAF Managed Rule | `mxgraph.aws4.waf_managed_rule` | AWS-managed rule groups |
| NF Endpoints | `mxgraph.aws4.network_firewall_endpoints` | Per-AZ firewall endpoints |
| Route53 DNS FW | `mxgraph.aws4.route_53_resolver_dns_firewall` | DNS-layer filtering |
| NACL | `mxgraph.aws4.network_access_control_list` | Subnet-level stateless rules |
