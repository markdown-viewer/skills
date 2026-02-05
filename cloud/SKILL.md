---
name: cloud
description: Create cloud architecture diagrams using drawio XML format with official cloud provider icons. Best for AWS, Azure, GCP, Alibaba Cloud architecture diagrams with proper service icons and layout conventions. Built on drawio with cloud-specific stencils. NOT for simple flowcharts (use mermaid) or network topology without cloud services (use network skill).
author: Cloud diagrams are powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Cloud Architecture Diagram Generator

**Quick Start:** Choose cloud provider → Add service icons from stencil library → Group services in regions/VPCs → Connect with data flow arrows → Wrap in ` ```drawio ` fence.

> ⚠️ **IMPORTANT:** Always use ` ```drawio ` code fence. NEVER use ` ```xml ` — it will NOT render as a diagram.

## Critical Rules

> 🔗 **This is a drawio-derived skill.** All structure, layout, and edge routing rules inherit from [drawio SKILL.md](../drawio/SKILL.md). Read the base rules first.

**Cloud-specific additions:**
- Check [stencils/README.md](../drawio/stencils/README.md) for exact cloud stencil names (e.g., `mxgraph.aws4.*`, `mxgraph.gcp2.*`)
- Use `fillColor=none;` for VPC/region containers to avoid covering child services

## Cloud Architecture Types

| Type | Purpose | Stencil Library | Example |
|------|---------|-----------------|---------|
| AWS | Amazon Web Services architecture | `mxgraph.aws4.*` (1031 icons) | [aws-basic.md](examples/aws-basic.md) |
| AWS Serverless | Event-driven serverless architecture | `mxgraph.aws4.*` | [aws-serverless.md](examples/aws-serverless.md) |
| Azure | Microsoft Azure architecture | `mxgraph.azure.*`, `mxgraph.mscae.*`, `mxgraph.office.*` | [azure-hybrid-network.md](examples/azure-hybrid-network.md) |
| GCP | Google Cloud Platform architecture | `mxgraph.gcp2.*` (297 icons) | [gcp-log-processing.md](examples/gcp-log-processing.md) |
| Alibaba Cloud | Alibaba Cloud architecture | `mxgraph.alibaba_cloud.*` (310 icons) | [alibaba-web-app.md](examples/alibaba-web-app.md) |
| IBM Cloud | IBM Cloud architecture | `mxgraph.ibm.*`, `mxgraph.ibm_cloud.*` (118 icons) | [ibm-kubernetes.md](examples/ibm-kubernetes.md) |
| Kubernetes | Container orchestration | `mxgraph.kubernetes.*` (40 icons) | [kubernetes-microservices.md](examples/kubernetes-microservices.md) |
| OpenStack | Private cloud infrastructure | `mxgraph.openstack.*` (18 icons) | [openstack-basic.md](examples/openstack-basic.md) |
