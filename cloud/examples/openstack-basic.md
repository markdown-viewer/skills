# OpenStack Basic Infrastructure

Basic OpenStack deployment with Neutron networking, Nova compute, Cinder block storage, and Swift object storage.

## Key Elements

| Component | Stencil |
|-----------|---------|
| Router | `mxgraph.openstack.neutron_router` |
| Floating IP | `mxgraph.openstack.neutron_floatingip` |
| Security Group | `mxgraph.openstack.neutron_securitygroup` |
| VM (Nova) | `mxgraph.openstack.nova_server` |
| Volume (Cinder) | `mxgraph.openstack.cinder_volume` |
| Object Storage | `mxgraph.openstack.swift_container` |

## Example

```plantuml
@startuml
left to right direction

cloud "Internet" as internet

mxgraph.openstack.neutron_floatingip "Floating IP" as fip
mxgraph.openstack.neutron_router "Router" as router

rectangle "Internal Network" {
  rectangle "Subnet 10.0.0.0/24" {
    mxgraph.openstack.neutron_securitygroup "Security\nGroup" as sg
    mxgraph.openstack.nova_server "Web Server" as vm1
    mxgraph.openstack.nova_server "App Server" as vm2
  }
}

mxgraph.openstack.cinder_volume "Volume 1" as vol1
mxgraph.openstack.cinder_volume "Volume 2" as vol2
mxgraph.openstack.swift_container "Object\nStorage" as swift

internet --> router
fip ..> router
router --> sg
sg ..> vm1
sg ..> vm2
vm1 --> vol1
vm2 --> vol2
vm2 ..> swift
@enduml
```

## Pattern Notes

1. **OpenStack stencils**: `mxgraph.openstack.<service>_<resource>` — e.g. `neutron_router`, `nova_server`, `cinder_volume`
2. **Network hierarchy**: Internal Network → Subnet as nested rectangles, Security Group inside subnet
3. **Security Group links**: `..>` dashed to indicate security policy association
4. **Storage outside network**: Cinder volumes and Swift containers placed outside the network boundary

## Related Icons

| Icon | Stencil | Use When |
|------|---------|----------|
| Neutron Net | `mxgraph.openstack.neutron_net` | Virtual network |
| Neutron Subnet | `mxgraph.openstack.neutron_subnet` | Subnet definition |
| Neutron Port | `mxgraph.openstack.neutron_port` | Network port |
| Nova Keypair | `mxgraph.openstack.nova_keypair` | SSH key management |
| Heat AutoScaling | `mxgraph.openstack.heat_autoscalinggroup` | Auto scaling group |
| Designate Zone | `mxgraph.openstack.designate_zone` | DNS zone management |
