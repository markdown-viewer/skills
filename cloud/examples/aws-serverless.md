# AWS Serverless Architecture

Event-driven serverless architecture with API Gateway, Lambda, DynamoDB, and S3.

## Key Elements

| Component | Stencil | fillColor |
|-----------|---------|----------|
| Region | `grIcon=mxgraph.aws4.group_region` | `strokeColor=#00A4A6` |
| Client App | `shape=mxgraph.aws4.mobile_client` | `#232F3E` |
| Cognito | `resIcon=mxgraph.aws4.cognito` | `#DD344C` |
| API Gateway | `resIcon=mxgraph.aws4.api_gateway` | `#E7157B` |
| Lambda | `resIcon=mxgraph.aws4.lambda` | `#ED7100` |
| DynamoDB | `resIcon=mxgraph.aws4.dynamodb` | `#3B48CC` |
| S3 | `resIcon=mxgraph.aws4.s3` | `#7AA116` |
| SQS | `resIcon=mxgraph.aws4.sqs` | `#E7157B` |
| SNS | `resIcon=mxgraph.aws4.sns` | `#E7157B` |
| EventBridge | `resIcon=mxgraph.aws4.eventbridge` | `#E7157B` |
| Step Functions | `resIcon=mxgraph.aws4.step_functions` | `#E7157B` |
| CloudWatch | `resIcon=mxgraph.aws4.cloudwatch` | `#E7157B` |

**Icon pattern:** `shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.<name>`. Sub-components use direct `shape=mxgraph.aws4.<name>` (smaller, no gradient).

**Async edges:** Use `dashed=1` for event-driven connections (S3 triggers, SQS polling, DynamoDB Streams) vs solid for sync calls.

## Example

```drawio
<mxfile><diagram id="aws-serverless" name="Serverless"><mxGraphModel dx="1000" dy="700" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="700" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="region" value="AWS Region" style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_region;strokeColor=#00A4A6;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#147EBA;dashed=1;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;" vertex="1" parent="1"><mxGeometry x="160" y="40" width="880" height="620" as="geometry"/></mxCell>
  <mxCell id="client" value="Client App" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#232F3E;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.mobile_client;" vertex="1" parent="1"><mxGeometry x="40" y="200" width="50" height="78" as="geometry"/></mxCell>
  <mxCell id="cognito" value="Cognito" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F54749;gradientDirection=north;fillColor=#DD344C;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cognito;" vertex="1" parent="region"><mxGeometry x="60" y="40" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="apigw" value="API Gateway" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F34482;gradientDirection=north;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.api_gateway;" vertex="1" parent="region"><mxGeometry x="60" y="190" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="lambda-api" value="Lambda&#xa;(API Handler)" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" vertex="1" parent="region"><mxGeometry x="230" y="190" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="dynamodb" value="DynamoDB" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#4D72F3;gradientDirection=north;fillColor=#3B48CC;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.dynamodb;" vertex="1" parent="region"><mxGeometry x="420" y="190" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="s3-uploads" value="S3&#xa;(Uploads)" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#60A337;gradientDirection=north;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" vertex="1" parent="region"><mxGeometry x="60" y="380" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="lambda-s3" value="Lambda&#xa;(S3 Trigger)" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" vertex="1" parent="region"><mxGeometry x="230" y="380" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="sqs" value="SQS Queue" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F34482;gradientDirection=north;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.sqs;" vertex="1" parent="region"><mxGeometry x="420" y="380" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="lambda-worker" value="Lambda&#xa;(Worker)" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" vertex="1" parent="region"><mxGeometry x="610" y="380" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="sns" value="SNS Topic" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F34482;gradientDirection=north;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.sns;" vertex="1" parent="region"><mxGeometry x="610" y="190" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="cloudwatch" value="CloudWatch" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F34482;gradientDirection=north;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cloudwatch;" vertex="1" parent="region"><mxGeometry x="760" y="40" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="eventbridge" value="EventBridge" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F34482;gradientDirection=north;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.eventbridge;" vertex="1" parent="region"><mxGeometry x="760" y="190" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="step-fn" value="Step&#xa;Functions" style="outlineConnect=0;fontColor=#232F3E;gradientColor=#F34482;gradientDirection=north;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.step_functions;" vertex="1" parent="region"><mxGeometry x="760" y="380" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="link-client-cognito" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#DD344C;exitX=1;exitY=0.25;entryX=0;entryY=0.5;" edge="1" parent="1" source="client" target="cognito"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="130" y="220"/><mxPoint x="130" y="110"/></Array></mxGeometry></mxCell>
  <mxCell id="link-client-apigw" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;exitX=1;exitY=0.5;entryX=0;entryY=0.5;" edge="1" parent="1" source="client" target="apigw"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-apigw-lambda" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" edge="1" parent="1" source="apigw" target="lambda-api"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lambda-dynamo" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#3B48CC;" edge="1" parent="1" source="lambda-api" target="dynamodb"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-client-s3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#7AA116;exitX=1;exitY=0.75;entryX=0;entryY=0.5;" edge="1" parent="1" source="client" target="s3-uploads"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="130" y="258"/><mxPoint x="130" y="450"/></Array></mxGeometry></mxCell>
  <mxCell id="link-s3-lambda" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;dashed=1;" edge="1" parent="1" source="s3-uploads" target="lambda-s3"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lambda-s3-sqs" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;" edge="1" parent="1" source="lambda-s3" target="sqs"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sqs-worker" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;dashed=1;" edge="1" parent="1" source="sqs" target="lambda-worker"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-worker-sns" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;" edge="1" parent="1" source="lambda-worker" target="sns"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dynamo-sns" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;dashed=1;" edge="1" parent="1" source="dynamodb" target="sns"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sns-eventbridge" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;" edge="1" parent="1" source="sns" target="eventbridge"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-eventbridge-stepfn" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;dashed=1;" edge="1" parent="1" source="eventbridge" target="step-fn"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```

## Pattern Notes

1. **Flat layout**: Serverless architectures use Region container (no VPC/subnet needed)
2. **Dashed = async**: `dashed=1` for event-driven connections, solid for sync API calls
3. **Color-coded edges**: Match `strokeColor` to service category color
4. **External clients**: Place outside the Region boundary
