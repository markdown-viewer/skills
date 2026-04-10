# Slate Dark Style

**Style**: Dark slate background (#1e293b), muted color borders, subtle tinted fills, 8px radius, professional dark mode
**Best for**: Enterprise dark mode, internal tools, developer dashboards, serious documentation

## Style Characteristics

| Property | Value |
|---|---|
| Fill | Very subtle tinted fills (6% opacity), dark base |
| Border | 1px solid, muted-bright colors |
| Radius | 8px layers, 6px boxes |
| Shadow | None — dark backgrounds don't need depth shadows |
| Text | Light (#cbd5e1) on dark backgrounds |
| Palette | Muted blue / Amber / Emerald / Pink / Lavender on dark slate |

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative; background: #1e293b; padding: 20px; border-radius: 10px;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 12px; }.arch-sidebar { width: 165px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 22px; font-weight: bold; color: #e2e8f0; margin-bottom: 16px; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 8px; }.arch-layer-title { font-size: 13px; font-weight: bold; margin-bottom: 10px; text-align: center; }
    .arch-grid { display: grid; gap: 8px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 6px; padding: 8px; text-align: center; font-size: 11px; font-weight: 600; line-height: 1.35; color: #cbd5e1; background: rgba(51, 65, 85, 0.6); border: 1px solid rgba(148, 163, 184, 0.3); }.arch-box.highlight { background: rgba(59, 130, 246, 0.2); border: 1px solid #60a5fa; color: #93c5fd; }.arch-box.tech { font-size: 10px; color: #94a3b8; background: rgba(30, 41, 59, 0.6); }
    .arch-layer.external { background: rgba(51, 65, 85, 0.2); border: 1px dashed #475569; }.arch-layer.external .arch-layer-title { color: #94a3b8; }.arch-layer.user { background: rgba(59, 130, 246, 0.06); border: 1px solid #60a5fa; }.arch-layer.user .arch-layer-title { color: #93c5fd; }.arch-layer.application { background: rgba(245, 158, 11, 0.06); border: 1px solid #fbbf24; }.arch-layer.application .arch-layer-title { color: #fcd34d; }.arch-layer.ai { background: rgba(16, 185, 129, 0.06); border: 1px solid #34d399; }.arch-layer.ai .arch-layer-title { color: #6ee7b7; }.arch-layer.data { background: rgba(236, 72, 153, 0.06); border: 1px solid #f472b6; }.arch-layer.data .arch-layer-title { color: #f9a8d4; }.arch-layer.infra { background: rgba(139, 92, 246, 0.06); border: 1px solid #a78bfa; }.arch-layer.infra .arch-layer-title { color: #c4b5fd; }
    .arch-sidebar-panel { border-radius: 8px; padding: 10px; background: rgba(51, 65, 85, 0.3); border: 1px solid #475569; margin-bottom: 8px; }.arch-sidebar-title { font-size: 12px; font-weight: bold; text-align: center; color: #94a3b8; margin-bottom: 6px; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #cbd5e1; background: rgba(30, 41, 59, 0.5); padding: 5px; border-radius: 4px; margin: 3px 0; border: 1px solid rgba(51, 65, 85, 0.6); }.arch-sidebar-item.metric { background: rgba(59, 130, 246, 0.12); border: 1px solid rgba(96, 165, 250, 0.4); color: #93c5fd; font-weight: 600; }
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
