# Left Sidebar Layout

**Layout**: Left sidebar + main content area
**Best for**: Systems with operations/monitoring emphasis, DevOps-centric views

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 12px; }.arch-sidebar { width: 180px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 4px; border: 1px solid #ccc; background: #fafafa; }.arch-layer-title { font-size: 12px; font-weight: 600; color: #555; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }.arch-box.tech { font-size: 10px; color: #666; }
    .arch-sidebar-panel { border-radius: 4px; padding: 10px; background: #fafafa; border: 1px solid #ccc; margin-bottom: 8px; }.arch-sidebar-title { font-size: 11px; font-weight: 600; text-align: center; color: #555; margin-bottom: 6px; text-transform: uppercase; letter-spacing: 0.3px; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #666; background: #fff; padding: 4px; border-radius: 3px; margin: 3px 0; border: 1px solid #eee; }
  </style>
  <div class="arch-title">Platform Architecture</div>
  <div class="arch-wrapper">
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">DevOps</div><div class="arch-sidebar-item">CI/CD Pipeline</div><div class="arch-sidebar-item">GitOps</div><div class="arch-sidebar-item">IaC</div><div class="arch-sidebar-item">Deployment</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Monitoring</div><div class="arch-sidebar-item">Metrics</div><div class="arch-sidebar-item">Alerting</div><div class="arch-sidebar-item">Dashboards</div><div class="arch-sidebar-item">Log Aggregation</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">SRE</div><div class="arch-sidebar-item">SLO/SLI</div><div class="arch-sidebar-item">Incident Response</div><div class="arch-sidebar-item">Runbooks</div></div>
    </div>
    <div class="arch-main">
      <div class="arch-layer">
        <div class="arch-layer-title">Client Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Web Frontend</div><div class="arch-box">Mobile App</div><div class="arch-box">Third-party SDK</div><div class="arch-box">Webhook Consumer</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">API Layer</div>
        <div class="arch-grid arch-grid-3"><div class="arch-box highlight">API Gateway</div><div class="arch-box">GraphQL Server</div><div class="arch-box">WebSocket Server</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Service Layer</div>
        <div class="arch-grid arch-grid-5"><div class="arch-box">Auth Service</div><div class="arch-box">Core Service</div><div class="arch-box">Search Service</div><div class="arch-box">Notification</div><div class="arch-box">Billing</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Data Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">PostgreSQL</div><div class="arch-box">Redis</div><div class="arch-box">Elasticsearch</div><div class="arch-box">Object Store</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Platform Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Kubernetes</div><div class="arch-box">Service Mesh</div><div class="arch-box">Message Broker</div><div class="arch-box">DNS / CDN</div></div>
      </div>
    </div>
  </div>
</div>
