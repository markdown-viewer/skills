# AWS Basic Architecture

Shows a typical three-tier AWS web application with load balancer, compute, and database layers.

## Key Elements

- **Region Container**: `strokeColor=#147EBA;dashed=1;fillColor=none`
- **VPC Container**: `strokeColor=#248814;fillColor=#E9F3E6`
- **ALB**: `resIcon=mxgraph.aws4.application_load_balancer`
- **EC2**: `resIcon=mxgraph.aws4.ec2`
- **RDS**: `resIcon=mxgraph.aws4.rds`
- **S3**: `resIcon=mxgraph.aws4.s3`

## AWS Icon Pattern

All AWS4 icons follow this pattern:
```
shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.<service_name>;
fillColor=<category_color>;strokeColor=#ffffff;
verticalLabelPosition=bottom;verticalAlign=top;
```

## Example

Simple web application with ALB, EC2 Auto Scaling, and RDS:

```drawio
<mxfile><diagram id="aws-basic" name="AWS Basic"><mxGraphModel dx="1000" dy="700" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1200" pageHeight="800" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="region" value="AWS Region (us-east-1)" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=#147EBA;strokeWidth=2;fillColor=none;dashed=1;verticalAlign=top;fontSize=14;fontStyle=1;fontColor=#147EBA;" parent="1" vertex="1"><mxGeometry x="40" y="40" width="720" height="460" as="geometry"/></mxCell>
  <mxCell id="vpc" value="VPC (10.0.0.0/16)" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=#248814;strokeWidth=2;fillColor=#E9F3E6;verticalAlign=top;fontSize=12;fontStyle=1;fontColor=#248814;" parent="1" vertex="1"><mxGeometry x="60" y="80" width="680" height="400" as="geometry"/></mxCell>
  <mxCell id="az1" value="Availability Zone A" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=#147EBA;strokeWidth=1;fillColor=#EDF6FC;dashed=1;verticalAlign=top;fontSize=11;fontColor=#147EBA;" parent="1" vertex="1"><mxGeometry x="80" y="120" width="200" height="340" as="geometry"/></mxCell>
  <mxCell id="az2" value="Availability Zone B" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=#147EBA;strokeWidth=1;fillColor=#EDF6FC;dashed=1;verticalAlign=top;fontSize=11;fontColor=#147EBA;" parent="1" vertex="1"><mxGeometry x="300" y="120" width="200" height="340" as="geometry"/></mxCell>
  <mxCell id="users" value="Users" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#232F3E;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.users;" parent="1" vertex="1"><mxGeometry x="-60" y="200" width="50" height="50" as="geometry"/></mxCell>
  <mxCell id="cloudfront" value="CloudFront" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cloudfront;" parent="1" vertex="1"><mxGeometry x="520" y="140" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="alb" value="Application&#xa;Load Balancer" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.application_load_balancer;" parent="1" vertex="1"><mxGeometry x="520" y="260" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="ec2-1" value="EC2" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.ec2;" parent="1" vertex="1"><mxGeometry x="140" y="180" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="ec2-2" value="EC2" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.ec2;" parent="1" vertex="1"><mxGeometry x="360" y="180" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="rds-primary" value="RDS Primary" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#3B48CC;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.rds;" parent="1" vertex="1"><mxGeometry x="140" y="340" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="rds-standby" value="RDS Standby" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#3B48CC;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.rds;" parent="1" vertex="1"><mxGeometry x="360" y="340" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="s3" value="S3 Bucket" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" parent="1" vertex="1"><mxGeometry x="620" y="340" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="link-users-cf" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="users" target="cloudfront" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-cf-alb" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="cloudfront" target="alb" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-alb-ec2-1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="alb" target="ec2-1" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-alb-ec2-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="alb" target="ec2-2" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ec2-1-rds" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="ec2-1" target="rds-primary" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ec2-2-rds" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="ec2-2" target="rds-primary" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-rds-sync" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;startArrow=classic;strokeWidth=2;strokeColor=#3B48CC;dashed=1;" parent="1" source="rds-primary" target="rds-standby" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-ec2-s3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="ec2-1" target="s3" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="170" y="290"/><mxPoint x="650" y="290"/></Array></mxGeometry></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
