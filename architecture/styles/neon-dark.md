# Neon Dark Style

**Style**: Dark slate background (#0f172a), neon-bright borders, semi-transparent fills, 8px radius, glow shadows
**Best for**: Tech talks, developer conferences, gaming platforms, cybersecurity dashboards

## Style Characteristics

| Property | Value |
|---|---|
| Fill | Semi-transparent dark with rgba overlays |
| Border | 1px solid neon-bright colors |
| Radius | 8px layers, 6px boxes |
| Shadow | Colored glow `0 0 12px rgba(color, 0.15)` |
| Text | Light (#e2e8f0) on dark backgrounds |
| Palette | Neon cyan / Amber / Emerald / Magenta / Violet on dark slate |

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative; background: #0f172a; padding: 20px; border-radius: 12px;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 12px; }.arch-sidebar { width: 165px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 22px; font-weight: bold; color: #f1f5f9; margin-bottom: 16px; letter-spacing: 1px; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 8px; }.arch-layer-title { font-size: 13px; font-weight: bold; margin-bottom: 10px; text-align: center; }
    .arch-grid { display: grid; gap: 8px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 6px; padding: 8px; text-align: center; font-size: 11px; font-weight: 600; line-height: 1.35; color: #e2e8f0; background: rgba(30, 41, 59, 0.8); border: 1px solid rgba(148, 163, 184, 0.2); }.arch-box.highlight { background: rgba(250, 204, 21, 0.15); border: 1px solid #facc15; color: #fef08a; }.arch-box.tech { font-size: 10px; color: #94a3b8; background: rgba(15, 23, 42, 0.6); }
    .arch-layer.external { background: rgba(51, 65, 85, 0.3); border: 1px dashed #475569; }.arch-layer.external .arch-layer-title { color: #94a3b8; }.arch-layer.user { background: rgba(14, 165, 233, 0.1); border: 1px solid #0ea5e9; box-shadow: 0 0 12px rgba(14, 165, 233, 0.15); }.arch-layer.user .arch-layer-title { color: #7dd3fc; }.arch-layer.application { background: rgba(245, 158, 11, 0.1); border: 1px solid #f59e0b; box-shadow: 0 0 12px rgba(245, 158, 11, 0.15); }.arch-layer.application .arch-layer-title { color: #fcd34d; }.arch-layer.ai { background: rgba(16, 185, 129, 0.1); border: 1px solid #10b981; box-shadow: 0 0 12px rgba(16, 185, 129, 0.15); }.arch-layer.ai .arch-layer-title { color: #6ee7b7; }.arch-layer.data { background: rgba(236, 72, 153, 0.1); border: 1px solid #ec4899; box-shadow: 0 0 12px rgba(236, 72, 153, 0.15); }.arch-layer.data .arch-layer-title { color: #f9a8d4; }.arch-layer.infra { background: rgba(139, 92, 246, 0.1); border: 1px solid #8b5cf6; box-shadow: 0 0 12px rgba(139, 92, 246, 0.15); }.arch-layer.infra .arch-layer-title { color: #c4b5fd; }
    .arch-sidebar-panel { border-radius: 8px; padding: 10px; background: rgba(30, 41, 59, 0.6); border: 1px solid #334155; margin-bottom: 8px; }.arch-sidebar-title { font-size: 12px; font-weight: bold; text-align: center; color: #94a3b8; margin-bottom: 6px; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #cbd5e1; background: rgba(15, 23, 42, 0.5); padding: 5px; border-radius: 4px; margin: 3px 0; border: 1px solid rgba(51, 65, 85, 0.5); }.arch-sidebar-item.metric { background: rgba(16, 185, 129, 0.15); border: 1px solid rgba(16, 185, 129, 0.4); color: #6ee7b7; font-weight: 600; }
  </style>
  <div class="arch-title">System Architecture</div>
  <div class="arch-wrapper">
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Monitoring</div><div class="arch-sidebar-item">App Metrics</div><div class="arch-sidebar-item">Perf Tracking</div><div class="arch-sidebar-item">Health Checks</div><div class="arch-sidebar-item">Alerts</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Analytics</div><div class="arch-sidebar-item">User Behavior</div><div class="arch-sidebar-item">Business KPIs</div><div class="arch-sidebar-item">Tech Metrics</div><div class="arch-sidebar-item">Reports</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Ops</div><div class="arch-sidebar-item">CI/CD Pipeline</div><div class="arch-sidebar-item">Deployment</div><div class="arch-sidebar-item">Config</div><div class="arch-sidebar-item">Maintenance</div></div>
    </div>
    <div class="arch-main">
      <div class="arch-layer user">
        <div class="arch-layer-title">User Interface Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Web App<br><small>React/Vue</small></div><div class="arch-box">Mobile App<br><small>React Native</small></div><div class="arch-box">Desktop App<br><small>Electron</small></div><div class="arch-box">API Client<br><small>REST/GraphQL</small></div></div>
      </div>
      <div class="arch-layer application">
        <div class="arch-layer-title">Application Services</div>
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
        <div class="arch-layer-title">Infrastructure</div>
        <div class="arch-grid arch-grid-5"><div class="arch-box tech">Container<br><small>Docker/K8s</small></div><div class="arch-box tech">Load Balancer<br><small>Nginx</small></div><div class="arch-box tech">Message Queue<br><small>RabbitMQ</small></div><div class="arch-box tech">Logging<br><small>ELK Stack</small></div><div class="arch-box tech">CDN<br><small>CloudFlare</small></div></div>
      </div>
      <div class="arch-layer external">
        <div class="arch-layer-title">External Services</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box tech">Third-party APIs<br><small>Payment/Auth</small></div><div class="arch-box tech">Cloud Services<br><small>AWS/Azure</small></div><div class="arch-box tech">SaaS Tools<br><small>Analytics</small></div><div class="arch-box tech">Integrations<br><small>Webhooks</small></div></div>
      </div>
    </div>
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Security</div><div class="arch-sidebar-item">Authentication</div><div class="arch-sidebar-item">Authorization</div><div class="arch-sidebar-item">Encryption</div><div class="arch-sidebar-item">Network Sec</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Compliance</div><div class="arch-sidebar-item">Audit Logging</div><div class="arch-sidebar-item">Data Privacy</div><div class="arch-sidebar-item">Regulatory</div><div class="arch-sidebar-item">Standards</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Backup</div><div class="arch-sidebar-item">Data Backup</div><div class="arch-sidebar-item">Disaster Recovery</div><div class="arch-sidebar-item">HA</div><div class="arch-sidebar-item">Failover</div></div>
    </div>
  </div>
</div>
