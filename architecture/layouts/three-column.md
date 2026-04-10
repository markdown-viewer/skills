# Three-Column Layout

**Layout**: Left sidebar + center main + right sidebar
**Best for**: Complex systems with cross-cutting concerns and monitoring sidebars

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 12px; }.arch-sidebar { width: 165px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 4px; border: 1px solid #ccc; background: #fafafa; }.arch-layer-title { font-size: 12px; font-weight: 600; color: #555; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }.arch-box.tech { font-size: 10px; color: #666; }
    .arch-sidebar-panel { border-radius: 4px; padding: 10px; background: #fafafa; border: 1px solid #ccc; margin-bottom: 8px; }.arch-sidebar-title { font-size: 11px; font-weight: 600; text-align: center; color: #555; margin-bottom: 6px; text-transform: uppercase; letter-spacing: 0.3px; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #666; background: #fff; padding: 4px; border-radius: 3px; margin: 3px 0; border: 1px solid #eee; }
  </style>
  <div class="arch-title">System Architecture</div>
  <div class="arch-wrapper">
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Monitoring</div><div class="arch-sidebar-item">Application Metrics</div><div class="arch-sidebar-item">Performance Tracking</div><div class="arch-sidebar-item">Health Checks</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Analytics</div><div class="arch-sidebar-item">User Behavior</div><div class="arch-sidebar-item">Business KPIs</div><div class="arch-sidebar-item">Custom Reports</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Operations</div><div class="arch-sidebar-item">CI/CD Pipeline</div><div class="arch-sidebar-item">Deployment</div><div class="arch-sidebar-item">Configuration</div></div>
    </div>
    <div class="arch-main">
      <div class="arch-layer">
        <div class="arch-layer-title">User Interface Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Web App</div><div class="arch-box">Mobile App</div><div class="arch-box">Desktop App</div><div class="arch-box">API Client</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Application Layer</div>
        <div class="arch-grid arch-grid-3"><div class="arch-box">Business Logic</div><div class="arch-box highlight">API Gateway</div><div class="arch-box">Background Jobs</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Data Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Primary DB</div><div class="arch-box">Cache</div><div class="arch-box">Search</div><div class="arch-box">File Storage</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Infrastructure Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Containers</div><div class="arch-box">Load Balancer</div><div class="arch-box">Message Queue</div><div class="arch-box">CDN</div></div>
      </div>
    </div>
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Security</div><div class="arch-sidebar-item">Authentication</div><div class="arch-sidebar-item">Authorization</div><div class="arch-sidebar-item">Encryption</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Compliance</div><div class="arch-sidebar-item">Audit Logging</div><div class="arch-sidebar-item">Data Privacy</div><div class="arch-sidebar-item">Regulations</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Governance</div><div class="arch-sidebar-item">API Standards</div><div class="arch-sidebar-item">Code Review</div><div class="arch-sidebar-item">Documentation</div></div>
    </div>
  </div>
</div>
