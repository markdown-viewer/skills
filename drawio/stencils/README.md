# drawio Stencil Reference

## About Stencil Sizes

Each stencil is listed with its **original size** in pixels, e.g., `mxgraph.gcp2.bigquery` (172×153).

When using stencils in diagrams, you should **scale them proportionally** to fit your layout:

```xml
<!-- Original: 172×153, scaled to height 30 (ratio preserved) -->
<mxCell style="shape=mxgraph.gcp2.bigquery;..." vertex="1">
  <mxGeometry width="34" height="30" as="geometry"/>
</mxCell>
```

**Scale formula:** If original is W×H and target height is T, then: `width = W × (T / H)`

## Style Hints

Some stencils are **outline-only** (wireframe) or have no built-in brand color.
For these shapes you **must** set `fillColor` in the style, otherwise they will
render with the default fill (usually white) which may not be what you want.

Look for the ⚠️ markers in each category file.

## Stencil Categories

| Category | Count | Need fillColor | File |
|----------|-------|----------------|------|
| Alibaba Cloud | 310 | 310 | [alibaba_cloud.md](alibaba_cloud.md) |
| Android | 49 | 31 | [android.md](android.md) |
| Arrows | 34 | - | [arrows.md](arrows.md) |
| Atlassian | 26 | 26 | [atlassian.md](atlassian.md) |
| Aws | 99 | 91 | [aws.md](aws.md) |
| Aws2 | 250 | 1 | [aws2.md](aws2.md) |
| Aws3 | 293 | 277 | [aws3.md](aws3.md) |
| Aws3d | 16 | 13 | [aws3d.md](aws3d.md) |
| Aws4 | 1031 | 1028 | [aws4.md](aws4.md) |
| Azure | 89 | 89 | [azure.md](azure.md) |
| Basic | 30 | 30 | [basic.md](basic.md) |
| Bootstrap | 4 | 4 | [bootstrap.md](bootstrap.md) |
| Bpmn | 39 | - | [bpmn.md](bpmn.md) |
| Cabinets | 53 | - | [cabinets.md](cabinets.md) |
| Cisco | 296 | 293 | [cisco.md](cisco.md) |
| Cisco19 | 232 | 227 | [cisco19.md](cisco19.md) |
| Cisco Safe | 485 | 485 | [cisco_safe.md](cisco_safe.md) |
| Citrix | 97 | 4 | [citrix.md](citrix.md) |
| Citrix2 | 126 | 124 | [citrix2.md](citrix2.md) |
| Eip | 36 | - | [eip.md](eip.md) |
| Electrical | 527 | - | [electrical.md](electrical.md) |
| Floorplan | 44 | 43 | [floorplan.md](floorplan.md) |
| Flowchart | 34 | - | [flowchart.md](flowchart.md) |
| Fluid Power | 246 | - | [fluid_power.md](fluid_power.md) |
| Gcp | 66 | 64 | [gcp.md](gcp.md) |
| Gcp2 | 297 | 279 | [gcp2.md](gcp2.md) |
| Gmdl | 104 | 95 | [gmdl.md](gmdl.md) |
| Ibm | 8 | 8 | [ibm.md](ibm.md) |
| Ibm Cloud | 110 | 109 | [ibm_cloud.md](ibm_cloud.md) |
| Ios7 | 168 | - | [ios7.md](ios7.md) |
| Kubernetes | 40 | 40 | [kubernetes.md](kubernetes.md) |
| Kubernetes2 | 39 | 39 | [kubernetes2.md](kubernetes2.md) |
| Lean Mapping | 13 | - | [lean_mapping.md](lean_mapping.md) |
| Mockup | 104 | 31 | [mockup.md](mockup.md) |
| Mscae | 368 | 363 | [mscae.md](mscae.md) |
| Networks | 57 | 57 | [networks.md](networks.md) |
| Networks2 | 114 | 104 | [networks2.md](networks2.md) |
| Office | 449 | 362 | [office.md](office.md) |
| Openstack | 18 | 18 | [openstack.md](openstack.md) |
| Pid | 478 | - | [pid.md](pid.md) |
| Rack | 487 | 237 | [rack.md](rack.md) |
| Salesforce | 96 | 93 | [salesforce.md](salesforce.md) |
| Signs | 369 | - | [signs.md](signs.md) |
| Sitemap | 50 | - | [sitemap.md](sitemap.md) |
| Veeam | 580 | 367 | [veeam.md](veeam.md) |
| Vvd | 94 | 93 | [vvd.md](vvd.md) |
| Webicons | 176 | 71 | [webicons.md](webicons.md) |
| Weblogos | 178 | 93 | [weblogos.md](weblogos.md) |