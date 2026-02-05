---
name: architecture
description: Create layered architecture diagrams using HTML/CSS templates with color-coded layers and grid layouts. Best for visualizing system layers (User→Application→Data→Infrastructure), microservices architecture, and enterprise application design. NOT for pixel-perfect custom diagrams (use drawio), simple flowcharts (use mermaid), or data visualization (use vega).
author: Architecture Diagram Generator is powered by Markdown Viewer — the best multi-platform Markdown extension (Chrome/Edge/Firefox/VS Code) with diagrams, formulas, and one-click Word export. Learn more at https://xicilion.gitbook.io/markdown-viewer-extension/
---

# Architecture Diagram Generator
**Quick Start:** Create HTML structure with flexible layout (single/double/triple column) → Define CSS styles for layers and grids → Add content with categorized panels → Use semantic colors for different layers.
## Critical Rules
### Rule 1: Direct HTML Embedding
**IMPORTANT**: Write architecture diagrams as direct HTML in Markdown. **NEVER** use code blocks (` ```html `). The HTML should be embedded directly in the document without any fencing.
### Rule 2: No Empty Lines in HTML Structure
**CRITICAL**: Do NOT add any empty lines within the HTML architecture diagram structure. Keep the entire HTML block continuous to prevent parsing errors.
### Rule 3: Incremental Creation Approach
**RECOMMENDED**: Create architecture diagrams in multiple steps:
1. **First**: Create the overall framework (wrapper, sidebars, main structure) and define all CSS styles
2. **Second**: Add layer containers with titles
3. **Third**: Fill in components layer by layer
4. **Fourth**: Add detailed content and refinements
### Rule 4: Flexible Layout Structure
Architecture diagrams can use flexible layouts based on complexity:
- **Single Column**: Main content only (for simple architectures)
- **Two Column**: Main content + one sidebar (left or right)
- **Three Column**: Full layout with both sidebars (for complex systems)
  - **Left Sidebar**: Supporting systems (monitoring, operations, analytics)
  - **Main Content**: Core architecture layers (user, application, data, infrastructure)
  - **Right Sidebar**: Cross-cutting concerns (security, compliance, governance)
### Rule 5: Layer-Based Organization
Each layer should have:
- Clear semantic meaning (User, Application, AI/Logic, Data, Infrastructure)
- Consistent color coding
- Grid-based layout for components
- Appropriate nesting for sub-components
### Rule 6: Color Semantics
Use consistent colors for layer types:
- **User Layer**: Blue gradient (`#dbeafe` to `#bfdbfe`)
- **Application Layer**: Yellow/Orange gradient (`#fef3c7` to `#fde68a`)
- **AI/Logic Layer**: Green gradient (`#dcfce7` to `#bbf7d0`)
- **Data Layer**: Pink gradient (`#fce7f3` to `#fbcfe8`)
- **Infrastructure Layer**: Purple gradient (`#e0e7ff` to `#c7d2fe`)
- **External Services**: Gray gradient (`#f1f5f9` to `#e2e8f0`) with dashed border
## Basic Architecture Template
**USAGE NOTE**: Copy the HTML below directly into your Markdown document. Do NOT wrap it in code blocks. Remove all empty lines to keep it continuous.
<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 12px; }.arch-sidebar { width: 165px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 22px; font-weight: bold; color: #1e293b; margin-bottom: 16px; }
    .arch-layer { margin: 10px 0; padding: 14px; border-radius: 10px; box-shadow: 0 2px 8px rgba(15, 23, 42, 0.1); }.arch-layer-title { font-size: 14px; font-weight: bold; color: #1e293b; margin-bottom: 10px; text-align: center; }
    .arch-grid { display: grid; gap: 8px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 6px; padding: 8px; text-align: center; font-size: 11px; font-weight: 600; line-height: 1.35; color: #0f172a; background: rgba(255, 255, 255, 0.9); border: 1px solid rgba(15, 23, 42, 0.1); }.arch-box.highlight { background: linear-gradient(135deg, #fef08a 0%, #fde047 100%); border: 2px solid #eab308; }.arch-box.tech { font-size: 10px; background: rgba(255, 255, 255, 0.7); }
    .arch-layer.external { background: linear-gradient(135deg, #f1f5f9 0%, #e2e8f0 100%); border: 2px dashed #64748b; }.arch-layer.user { background: linear-gradient(135deg, #dbeafe 0%, #bfdbfe 100%); border: 2px solid #3b82f6; }.arch-layer.application { background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%); border: 2px solid #f59e0b; }.arch-layer.ai { background: linear-gradient(135deg, #dcfce7 0%, #bbf7d0 100%); border: 2px solid #22c55e; }.arch-layer.data { background: linear-gradient(135deg, #fce7f3 0%, #fbcfe8 100%); border: 2px solid #ec4899; }.arch-layer.infra { background: linear-gradient(135deg, #e0e7ff 0%, #c7d2fe 100%); border: 2px solid #6366f1; }
    .arch-sidebar-panel { border-radius: 8px; padding: 10px; background: linear-gradient(135deg, #f3f4f6 0%, #e5e7eb 100%); border: 2px solid #9ca3af; margin-bottom: 10px; box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05); }.arch-sidebar-title { font-size: 12px; font-weight: bold; text-align: center; color: #374151; margin-bottom: 6px; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #1f2937; background: rgba(255, 255, 255, 0.8); padding: 5px; border-radius: 4px; margin: 3px 0; border: 1px solid rgba(0, 0, 0, 0.05); }.arch-sidebar-item.metric { background: linear-gradient(135deg, #f0fdf4 0%, #dcfce7 100%); border: 1px solid #86efac; font-weight: 600; }
  </style>
  <div class="arch-title">System Architecture Overview</div>
  <div class="arch-wrapper">
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">📊 Monitoring</div><div class="arch-sidebar-item">Application Metrics</div><div class="arch-sidebar-item">Performance Tracking</div><div class="arch-sidebar-item">Health Checks</div><div class="arch-sidebar-item">Alert Management</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">📈 Analytics</div><div class="arch-sidebar-item">User Behavior</div><div class="arch-sidebar-item">Business KPIs</div><div class="arch-sidebar-item">Technical Metrics</div><div class="arch-sidebar-item">Custom Reports</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">🔄 Operations</div><div class="arch-sidebar-item">CI/CD Pipeline</div><div class="arch-sidebar-item">Deployment</div><div class="arch-sidebar-item">Configuration</div><div class="arch-sidebar-item">Maintenance</div></div>
    </div>
    <div class="arch-main">
      <div class="arch-layer user">
        <div class="arch-layer-title">User Interface Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Web App<br><small>React/Vue</small></div><div class="arch-box">Mobile App<br><small>React Native</small></div><div class="arch-box">Desktop App<br><small>Electron</small></div><div class="arch-box">API Client<br><small>REST/GraphQL</small></div></div>
      </div>
      <div class="arch-layer application">
        <div class="arch-layer-title">Application Services Layer</div>
        <div class="arch-grid arch-grid-3"><div class="arch-box">Business Logic<br><small>Core Services</small></div><div class="arch-box highlight">API Gateway<br><small>Routing & Auth</small></div><div class="arch-box">Background Jobs<br><small>Queue Processing</small></div></div>
      </div>
      <div class="arch-layer ai">
        <div class="arch-layer-title">Intelligence Layer</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">ML Models<br><small>Inference Engine</small></div><div class="arch-box">Rule Engine<br><small>Business Rules</small></div></div>
      </div>
      <div class="arch-layer data">
        <div class="arch-layer-title">Data Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box tech">Primary DB<br><small>PostgreSQL</small></div><div class="arch-box tech">Cache<br><small>Redis</small></div><div class="arch-box tech">Search<br><small>Elasticsearch</small></div><div class="arch-box tech">File Storage<br><small>S3/MinIO</small></div></div>
      </div>
      <div class="arch-layer infra">
        <div class="arch-layer-title">Infrastructure Layer</div>
        <div class="arch-grid arch-grid-5"><div class="arch-box tech">Container<br><small>Docker/K8s</small></div><div class="arch-box tech">Load Balancer<br><small>Nginx</small></div><div class="arch-box tech">Message Queue<br><small>RabbitMQ</small></div><div class="arch-box tech">Logging<br><small>ELK Stack</small></div><div class="arch-box tech">CDN<br><small>CloudFlare</small></div></div>
      </div>
      <div class="arch-layer external">
        <div class="arch-layer-title">External Services</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box tech">Third-party APIs<br><small>Payment/Auth</small></div><div class="arch-box tech">Cloud Services<br><small>AWS/Azure</small></div><div class="arch-box tech">SaaS Tools<br><small>Analytics</small></div><div class="arch-box tech">Integrations<br><small>Webhooks</small></div></div>
      </div>
    </div>
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">🔐 Security</div><div class="arch-sidebar-item">Authentication</div><div class="arch-sidebar-item">Authorization</div><div class="arch-sidebar-item">Data Encryption</div><div class="arch-sidebar-item">Network Security</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">📋 Compliance</div><div class="arch-sidebar-item">Audit Logging</div><div class="arch-sidebar-item">Data Privacy</div><div class="arch-sidebar-item">Regulatory</div><div class="arch-sidebar-item">Standards</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">💾 Backup</div><div class="arch-sidebar-item">Data Backup</div><div class="arch-sidebar-item">Disaster Recovery</div><div class="arch-sidebar-item">High Availability</div><div class="arch-sidebar-item">Failover</div></div>
    </div>
  </div>
</div>
```

## Advanced Features

**NOTE**: These advanced components require additional CSS styles. Add these to your `<style scoped>` section:

```css
.arch-product-group { display: flex; gap: 10px; }
.arch-product { flex: 1; border-radius: 8px; padding: 10px; background: rgba(255, 255, 255, 0.6); border: 1px dashed #d97706; }
.arch-product-title { font-size: 12px; font-weight: bold; color: #92400e; margin-bottom: 8px; text-align: center; }
.arch-subgroup { display: flex; gap: 8px; margin-top: 8px; }
.arch-subgroup-box { flex: 1; border-radius: 6px; padding: 8px; background: rgba(255, 255, 255, 0.5); border: 1px solid rgba(0, 0, 0, 0.08); }
.arch-subgroup-title { font-size: 10px; font-weight: bold; color: #374151; text-align: center; margin-bottom: 6px; }
.arch-user-types { display: flex; gap: 4px; justify-content: center; margin-top: 6px; }
.arch-user-tag { font-size: 9px; padding: 2px 6px; border-radius: 10px; background: rgba(59, 130, 246, 0.15); color: #1d4ed8; }
```

### Custom Product Groups
For complex applications with multiple products/modules:

```html
<div class="arch-product-group">
  <div class="arch-product">
    <div class="arch-product-title">🎯 Product A</div>
    <div class="arch-grid arch-grid-2">
      <div class="arch-box">Feature 1<br><small>Description</small></div>
      <div class="arch-box highlight">Feature 2<br><small>Key Feature</small></div>
    </div>
  </div>
  <div class="arch-product">
    <div class="arch-product-title">📊 Product B</div>
    <div class="arch-grid arch-grid-2">
      <div class="arch-box">Feature 3<br><small>Description</small></div>
      <div class="arch-box">Feature 4<br><small>Description</small></div>
    </div>
  </div>
</div>
```

### Sub-grouped Components
For detailed breakdowns within layers:

```html
<div class="arch-subgroup">
  <div class="arch-subgroup-box">
    <div class="arch-subgroup-title">Component Group A</div>
    <div class="arch-grid arch-grid-3">
      <div class="arch-box tech">Service 1<br><small>Details</small></div>
      <div class="arch-box tech">Service 2<br><small>Details</small></div>
      <div class="arch-box tech">Service 3<br><small>Details</small></div>
    </div>
  </div>
  <div class="arch-subgroup-box">
    <div class="arch-subgroup-title">Component Group B</div>
    <div class="arch-grid arch-grid-2">
      <div class="arch-box tech">Service 4<br><small>Details</small></div>
      <div class="arch-box tech">Service 5<br><small>Details</small></div>
    </div>
  </div>
</div>
```

### User Types/Tags
Add user type indicators:

```html
<div class="arch-user-types">
  <span class="arch-user-tag">Admin Users</span>
  <span class="arch-user-tag">End Users</span>
  <span class="arch-user-tag">API Clients</span>
  <span class="arch-user-tag">Partners</span>
</div>
```

### Metrics and KPIs
Highlight important metrics in sidebar:

```html
<div class="arch-sidebar-item metric">99.9% Uptime</div>
<div class="arch-sidebar-item metric">&lt;200ms Response</div>
<div class="arch-sidebar-item metric">1M+ Users</div>
```

## Styling Reference

### Layer Classes
- `.arch-layer.user` - Blue gradient for user-facing components
- `.arch-layer.application` - Yellow/Orange for application services  
- `.arch-layer.ai` - Green for AI/ML/Logic components
- `.arch-layer.data` - Pink for data storage and processing
- `.arch-layer.infra` - Purple for infrastructure components
- `.arch-layer.external` - Gray dashed for external dependencies

### Box Classes
- `.arch-box` - Standard component box
- `.arch-box.highlight` - Highlighted/key components (yellow)
- `.arch-box.tech` - Technical components (smaller text)

### Grid Classes
- `.arch-grid-2` to `.arch-grid-6` - 2 to 6 column responsive grids

### Sidebar Classes
- `.arch-sidebar-panel` - Panel container
- `.arch-sidebar-item` - Regular sidebar item
- `.arch-sidebar-item.metric` - Highlighted metric item

## Best Practices

### HTML Usage Guidelines

1. **Direct embedding only** - Always embed HTML directly in Markdown, never use ` ```html ` code blocks
2. **No empty lines in structure** - Keep the entire HTML block continuous without any empty lines
3. **Incremental development** - Build diagrams step by step:
   - Start with basic framework and layout structure (single/two/three column as needed)
   - Add empty layer containers with proper CSS classes
   - Fill in content layer by layer from top to bottom
   - Refine content and add highlights last

### Architecture Design

1. **Keep layers logically separated** - Each layer should represent a clear architectural tier
2. **Use consistent naming** - Follow naming conventions for components and services
3. **Highlight key components** - Use `.highlight` class for critical components
4. **Add technical details** - Include technology stack info in `<small>` tags
5. **Balance information density** - Don't overcrowd components with text
6. **Use icons sparingly** - Add emojis to titles for visual hierarchy
7. **Maintain color semantics** - Stick to the established color meanings
8. **Consider responsive design** - Grids automatically adapt to content

## Use Cases

- **Microservices Architecture** - Show service boundaries and dependencies
- **Enterprise Application Architecture** - Display multi-tier application structure  
- **Cloud Infrastructure** - Illustrate cloud service dependencies
- **Data Pipeline Architecture** - Show data flow through processing layers
- **AI/ML System Architecture** - Highlight ML components and data flows
- **Security Architecture** - Emphasize security controls across layers
- **DevOps Architecture** - Show CI/CD and deployment infrastructure