# Steel Blue Style

**Style**: Navy/steel/slate tri-tone system, blue-white gradients, 2px solid borders, 6px radius, corporate gravitas
**Best for**: Consulting reports, banking/finance systems, government projects, RFP proposals

## Style Characteristics

| Property | Value |
|---|---|
| Fill | Blue-gray gradients, conservative palette |
| Border | 2px solid, navy/steel tones |
| Radius | 6px layers, 4px boxes |
| Shadow | `0 1px 4px rgba(30,58,138,0.08)` subtle |
| Text | Navy (#1e293b) on light blue-white backgrounds |
| Palette | Navy / Steel / Slate / Silver — professional blue-gray spectrum |

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative; background: #f0f4f8; padding: 20px; border-radius: 8px; border: 1px solid #c8d6e5;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 12px; }.arch-sidebar { width: 165px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 22px; font-weight: bold; color: #1a365d; margin-bottom: 16px; font-family: Georgia, serif; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 6px; box-shadow: 0 1px 4px rgba(30, 58, 138, 0.08); }.arch-layer-title { font-size: 13px; font-weight: bold; margin-bottom: 10px; text-align: center; }
    .arch-grid { display: grid; gap: 8px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 4px; padding: 8px; text-align: center; font-size: 11px; font-weight: 600; line-height: 1.35; color: #1e293b; background: #ffffff; border: 1px solid #cbd5e1; }.arch-box.highlight { background: linear-gradient(135deg, #dbeafe 0%, #bfdbfe 100%); border: 2px solid #2563eb; }.arch-box.tech { font-size: 10px; color: #475569; background: #f1f5f9; }
    .arch-layer.external { background: linear-gradient(135deg, #edf2f7 0%, #e2e8f0 100%); border: 2px dashed #a0aec0; }.arch-layer.external .arch-layer-title { color: #718096; }.arch-layer.user { background: linear-gradient(135deg, #dbeafe 0%, #bfdbfe 100%); border: 2px solid #3b82f6; }.arch-layer.user .arch-layer-title { color: #1e40af; }.arch-layer.application { background: linear-gradient(135deg, #e0f2fe 0%, #bae6fd 100%); border: 2px solid #0284c7; }.arch-layer.application .arch-layer-title { color: #075985; }.arch-layer.ai { background: linear-gradient(135deg, #e0e7ff 0%, #c7d2fe 100%); border: 2px solid #6366f1; }.arch-layer.ai .arch-layer-title { color: #3730a3; }.arch-layer.data { background: linear-gradient(135deg, #ecfdf5 0%, #d1fae5 100%); border: 2px solid #10b981; }.arch-layer.data .arch-layer-title { color: #065f46; }.arch-layer.infra { background: linear-gradient(135deg, #f5f3ff 0%, #ede9fe 100%); border: 2px solid #7c3aed; }.arch-layer.infra .arch-layer-title { color: #5b21b6; }
    .arch-sidebar-panel { border-radius: 6px; padding: 10px; background: linear-gradient(135deg, #edf1f7 0%, #dde3eb 100%); border: 2px solid #8da3bd; margin-bottom: 8px; box-shadow: 0 1px 3px rgba(30, 58, 138, 0.06); }.arch-sidebar-title { font-size: 12px; font-weight: bold; text-align: center; color: #1a365d; margin-bottom: 6px; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #334155; background: #ffffff; padding: 5px; border-radius: 3px; margin: 3px 0; border: 1px solid #d1d9e4; }.arch-sidebar-item.metric { background: #dbeafe; border: 1px solid #93c5fd; color: #1e40af; font-weight: 600; }
  </style>
  <div class="arch-title">Enterprise System Architecture</div>
  <div class="arch-wrapper">
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Monitoring</div><div class="arch-sidebar-item">App Metrics</div><div class="arch-sidebar-item">Perf Tracking</div><div class="arch-sidebar-item">Health Checks</div><div class="arch-sidebar-item">Alerts</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Analytics</div><div class="arch-sidebar-item">User Behavior</div><div class="arch-sidebar-item">Business KPIs</div><div class="arch-sidebar-item">Tech Metrics</div><div class="arch-sidebar-item">Reports</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Ops</div><div class="arch-sidebar-item">CI/CD Pipeline</div><div class="arch-sidebar-item">Deployment</div><div class="arch-sidebar-item">Config</div><div class="arch-sidebar-item">Maintenance</div></div>
    </div>
    <div class="arch-main">
      <div class="arch-layer user">
        <div class="arch-layer-title">User Interface Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Web Portal<br><small>React/Angular</small></div><div class="arch-box">Mobile Client<br><small>iOS/Android</small></div><div class="arch-box">Admin Console<br><small>Internal Tools</small></div><div class="arch-box">API Client<br><small>REST/GraphQL</small></div></div>
      </div>
      <div class="arch-layer application">
        <div class="arch-layer-title">Application Services</div>
        <div class="arch-grid arch-grid-3"><div class="arch-box">Core Services<br><small>Business Rules</small></div><div class="arch-box highlight">API Gateway<br><small>Routing & Auth</small></div><div class="arch-box">Batch Processing<br><small>Scheduled Jobs</small></div></div>
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
        <div class="arch-grid arch-grid-4"><div class="arch-box tech">Partner APIs<br><small>B2B Gateway</small></div><div class="arch-box tech">Cloud Services<br><small>AWS/Azure</small></div><div class="arch-box tech">SaaS Tools<br><small>Analytics</small></div><div class="arch-box tech">Integrations<br><small>Webhooks</small></div></div>
      </div>
    </div>
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Security</div><div class="arch-sidebar-item">Authentication</div><div class="arch-sidebar-item">Authorization</div><div class="arch-sidebar-item">Encryption</div><div class="arch-sidebar-item">Network Sec</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Compliance</div><div class="arch-sidebar-item">Audit Logging</div><div class="arch-sidebar-item">Data Privacy</div><div class="arch-sidebar-item">Regulatory</div><div class="arch-sidebar-item">Standards</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Backup</div><div class="arch-sidebar-item">Data Backup</div><div class="arch-sidebar-item">Disaster Recovery</div><div class="arch-sidebar-item">HA</div><div class="arch-sidebar-item">Failover</div></div>
    </div>
  </div>
</div>
