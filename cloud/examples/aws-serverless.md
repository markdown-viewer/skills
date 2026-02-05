# AWS Serverless Architecture

Shows an event-driven serverless architecture with API Gateway, Lambda, DynamoDB, and S3.

## Key Elements

- **API Gateway**: `resIcon=mxgraph.aws4.api_gateway` (Pink `#E7157B`)
- **Lambda**: `resIcon=mxgraph.aws4.lambda` (Orange `#ED7100`)
- **DynamoDB**: `resIcon=mxgraph.aws4.dynamodb` (Blue `#3B48CC`)
- **S3**: `resIcon=mxgraph.aws4.s3` (Green `#7AA116`)
- **SQS**: `resIcon=mxgraph.aws4.sqs` (Pink `#E7157B`)
- **SNS**: `resIcon=mxgraph.aws4.sns` (Pink `#E7157B`)
- **EventBridge**: `resIcon=mxgraph.aws4.eventbridge` (Pink `#E7157B`)
- **Cognito**: `resIcon=mxgraph.aws4.cognito` (Red `#DD344C`)

## Connection Types

| Type | Style | Use Case |
|------|-------|----------|
| Sync Request | `strokeColor=#232F3E;strokeWidth=2` | API calls |
| Async Event | `strokeColor=#E7157B;dashed=1` | Event triggers |
| Data Flow | `strokeColor=#3B48CC;strokeWidth=2` | Database operations |

## Example

REST API with Lambda backend and DynamoDB:

```drawio
<mxfile><diagram id="aws-serverless" name="Serverless"><mxGraphModel dx="1000" dy="700" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="700" math="0" shadow="0"><root><mxCell id="0"/><mxCell id="1" parent="0"/>
  <mxCell id="region" value="AWS Region" style="rounded=1;whiteSpace=wrap;html=1;strokeColor=#147EBA;strokeWidth=2;fillColor=none;dashed=1;verticalAlign=top;fontSize=14;fontStyle=1;fontColor=#147EBA;" parent="1" vertex="1"><mxGeometry x="160" y="40" width="700" height="440" as="geometry"/></mxCell>
  <mxCell id="client" value="Client App" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#232F3E;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.mobile_client;" parent="1" vertex="1"><mxGeometry x="40" y="180" width="50" height="78" as="geometry"/></mxCell>
  <mxCell id="cognito" value="Cognito" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#DD344C;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cognito;" parent="1" vertex="1"><mxGeometry x="200" y="80" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="apigw" value="API Gateway" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.api_gateway;" parent="1" vertex="1"><mxGeometry x="200" y="200" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="lambda-api" value="Lambda&#xa;(API Handler)" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" parent="1" vertex="1"><mxGeometry x="360" y="200" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="dynamodb" value="DynamoDB" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#3B48CC;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.dynamodb;" parent="1" vertex="1"><mxGeometry x="520" y="200" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="s3-uploads" value="S3&#xa;(Uploads)" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" parent="1" vertex="1"><mxGeometry x="200" y="360" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="lambda-s3" value="Lambda&#xa;(S3 Trigger)" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" parent="1" vertex="1"><mxGeometry x="360" y="360" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="sqs" value="SQS Queue" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.sqs;" parent="1" vertex="1"><mxGeometry x="520" y="360" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="lambda-worker" value="Lambda&#xa;(Worker)" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" parent="1" vertex="1"><mxGeometry x="680" y="360" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="sns" value="SNS Topic" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.sns;" parent="1" vertex="1"><mxGeometry x="680" y="200" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="cloudwatch" value="CloudWatch" style="outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cloudwatch;" parent="1" vertex="1"><mxGeometry x="760" y="80" width="60" height="60" as="geometry"/></mxCell>
  <mxCell id="link-client-cognito" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#DD344C;" parent="1" source="client" target="cognito" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-client-apigw" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="client" target="apigw" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-apigw-lambda" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#232F3E;" parent="1" source="apigw" target="lambda-api" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lambda-dynamo" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#3B48CC;" parent="1" source="lambda-api" target="dynamodb" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-client-s3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#7AA116;" parent="1" source="client" target="s3-uploads" edge="1"><mxGeometry relative="1" as="geometry"><Array as="points"><mxPoint x="65" y="390"/></Array></mxGeometry></mxCell>
  <mxCell id="link-s3-lambda" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;dashed=1;" parent="1" source="s3-uploads" target="lambda-s3" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-lambda-s3-sqs" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;" parent="1" source="lambda-s3" target="sqs" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-sqs-worker" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;dashed=1;" parent="1" source="sqs" target="lambda-worker" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-worker-sns" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;" parent="1" source="lambda-worker" target="sns" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
  <mxCell id="link-dynamo-sns" style="edgeStyle=orthogonalEdgeStyle;rounded=0;html=1;endArrow=classic;strokeWidth=2;strokeColor=#E7157B;dashed=1;" parent="1" source="dynamodb" target="sns" edge="1"><mxGeometry relative="1" as="geometry"/></mxCell>
</root></mxGraphModel></diagram></mxfile>
```
