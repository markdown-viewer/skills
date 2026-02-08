# Alibaba Cloud Web Application Architecture

Three-tier web application with CDN, WAF, SLB, ECS, PolarDB, and Redis.

## Key Elements

| Component | Stencil | fillColor |
|-----------|---------|----------|
| User | `mxgraph.alibaba_cloud.user` | `#FF6A00` |
| CDN | `mxgraph.alibaba_cloud.cdn_content_distribution_network` | `#FF6A00` |
| WAF | `mxgraph.alibaba_cloud.waf_web_application_firewall` | `#E02020` |
| SLB | `mxgraph.alibaba_cloud.slb_server_load_balancer_01` | `#FF6A00` |
| ECS | `mxgraph.alibaba_cloud.ecs_elastic_compute_service` | `#FF6A00` |
| PolarDB | `mxgraph.alibaba_cloud.polardb` | `#00C1DE` |
| Redis | `mxgraph.alibaba_cloud.redis_kvstore` | `#00C1DE` |
| OSS | `mxgraph.alibaba_cloud.oss_object_storage_service` | `#00B42A` |
| NAT Gateway | `mxgraph.alibaba_cloud.nat_gateway` | `#5B5EA6` |
| DNS | `mxgraph.alibaba_cloud.dns_domain_name_system` | `#5B5EA6` |

**Icon pattern:** `shape=mxgraph.alibaba_cloud.<name>` directly (no `resourceIcon` wrapper). All icons require `fillColor`.

**Colors:** Compute/Network `#FF6A00`, Database/Cache `#00C1DE`, Storage `#00B42A`, Security `#E02020`, Infrastructure `#5B5EA6`. No built-in group containers — use plain dashed rectangles.

## Example

```drawio
<mxfile><diagram id="alibaba-web-app" name="Alibaba Cloud Web App"><mxGraphModel dx="1200" dy="800" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="800" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="ali-cloud" value="Alibaba Cloud" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=0;strokeColor=#FF6A00;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=14;fontStyle=1;fontColor=#FF6A00;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="1"><mxGeometry x="200" y="30" width="960" height="740" as="geometry"/></mxCell>
  <mxCell id="vpc" value="VPC (10.0.0.0/16)" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=1;strokeColor=#5B5EA6;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontStyle=0;fontColor=#5B5EA6;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="ali-cloud"><mxGeometry x="20" y="160" width="920" height="560" as="geometry"/></mxCell>
  <mxCell id="pub-zone" value="Public Zone" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=1;strokeColor=#7AA116;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontSize=11;fontColor=#7AA116;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="vpc"><mxGeometry x="20" y="40" width="880" height="160" as="geometry"/></mxCell>
  <mxCell id="priv-zone-1" value="Private Zone (AZ-A)" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=1;strokeColor=#147EBA;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontSize=11;fontColor=#147EBA;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="vpc"><mxGeometry x="20" y="230" width="420" height="300" as="geometry"/></mxCell>
  <mxCell id="priv-zone-2" value="Private Zone (AZ-B)" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;dashed=1;strokeColor=#147EBA;strokeWidth=1;verticalAlign=top;align=left;spacingLeft=10;fontSize=11;fontColor=#147EBA;container=1;collapsible=0;recursiveResize=0;" vertex="1" parent="vpc"><mxGeometry x="480" y="230" width="420" height="300" as="geometry"/></mxCell>
  <mxCell id="dns" value="Alibaba&#xa;Cloud DNS" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#5B5EA6;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.dns_domain_name_system;" vertex="1" parent="ali-cloud"><mxGeometry x="100" y="40" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="cdn" value="CDN" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#FF6A00;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.cdn_content_distribution_network;" vertex="1" parent="ali-cloud"><mxGeometry x="300" y="40" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="waf" value="WAF" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#E02020;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.waf_web_application_firewall;" vertex="1" parent="ali-cloud"><mxGeometry x="500" y="40" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="oss" value="OSS&#xa;(Static Assets)" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#00B42A;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.oss_object_storage_service;" vertex="1" parent="ali-cloud"><mxGeometry x="780" y="40" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="slb" value="SLB" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#FF6A00;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.slb_server_load_balancer_01;" vertex="1" parent="pub-zone"><mxGeometry x="160" y="50" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="nat-gw" value="NAT&#xa;Gateway" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#5B5EA6;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.nat_gateway;" vertex="1" parent="pub-zone"><mxGeometry x="700" y="50" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="ecs-1" value="ECS-1" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#FF6A00;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.ecs_elastic_compute_service;" vertex="1" parent="priv-zone-1"><mxGeometry x="60" y="50" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="ecs-2" value="ECS-2" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#FF6A00;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.ecs_elastic_compute_service;" vertex="1" parent="priv-zone-1"><mxGeometry x="280" y="50" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="polardb-primary" value="PolarDB&#xa;(Primary)" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#00C1DE;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.polardb;" vertex="1" parent="priv-zone-1"><mxGeometry x="140" y="190" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="ecs-3" value="ECS-3" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#FF6A00;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.ecs_elastic_compute_service;" vertex="1" parent="priv-zone-2"><mxGeometry x="60" y="50" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="ecs-4" value="ECS-4" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#FF6A00;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.ecs_elastic_compute_service;" vertex="1" parent="priv-zone-2"><mxGeometry x="280" y="50" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="redis" value="Redis&#xa;(Cache)" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#00C1DE;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.redis_kvstore;" vertex="1" parent="priv-zone-2"><mxGeometry x="60" y="190" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="polardb-standby" value="PolarDB&#xa;(Read-Only)" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#00C1DE;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.polardb;" vertex="1" parent="priv-zone-2"><mxGeometry x="280" y="190" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="users" value="Users" style="outlineConnect=0;fontColor=#232F3E;strokeColor=none;fillColor=#FF6A00;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.alibaba_cloud.user;" vertex="1" parent="1"><mxGeometry x="60" y="100" width="48" height="48" as="geometry"/></mxCell>
  <mxCell id="link-users-dns" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#FF6A00;" edge="1" parent="1" source="users" target="dns"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dns-cdn" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#FF6A00;" edge="1" parent="1" source="dns" target="cdn"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-cdn-oss" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#00B42A;" edge="1" parent="1" source="cdn" target="oss"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-cdn-waf" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E02020;" edge="1" parent="1" source="cdn" target="waf"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-waf-slb" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E02020;" edge="1" parent="1" source="waf" target="slb"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-slb-ecs1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#FF6A00;" edge="1" parent="1" source="slb" target="ecs-1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-slb-ecs3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#FF6A00;" edge="1" parent="1" source="slb" target="ecs-3"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ecs1-polardb" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#00C1DE;" edge="1" parent="1" source="ecs-1" target="polardb-primary"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ecs3-redis" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#00C1DE;" edge="1" parent="1" source="ecs-3" target="redis"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-polardb-rep" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#00C1DE;dashed=1;" edge="1" parent="1" source="polardb-primary" target="polardb-standby"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ecs2-polardb" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#00C1DE;" edge="1" parent="1" source="ecs-2" target="polardb-primary"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ecs4-redis" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#00C1DE;" edge="1" parent="1" source="ecs-4" target="redis"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Pattern Notes

1. **fillColor required**: Icons render invisible without it
2. **Direct shape pattern**: `shape=mxgraph.alibaba_cloud.<name>` (no `resourceIcon` wrapper)
3. **No group containers**: Use dashed rectangles for VPC/subnet boundaries
4. **Multi-AZ**: ECS across two private zones, SLB distributes traffic
5. **Edge colors**: Match `strokeColor` to target service category
