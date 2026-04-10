# Ember Warm Style

**Style**: Amber-orange-terracotta warm spectrum, earthy gradients, 2px solid borders, 6px radius, organic warmth
**Best for**: Retail/e-commerce, education platforms, lifestyle brands, cultural institutions

## Style Characteristics

| Property | Value |
|---|---|
| Fill | Warm amber-to-orange gradients, earthy accents |
| Border | 2px solid, warm amber/brown tones |
| Radius | 6px layers, 5px boxes |
| Shadow | `0 2px 6px rgba(120,53,15,0.08)` warm |
| Text | Dark clay (#44220e) on warm backgrounds |
| Palette | Amber / Burnt Orange / Coral / Sage / Stone |

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative; background: #faf6f1; padding: 20px; border-radius: 8px; border: 1px solid #d4c4a8;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 12px; }.arch-sidebar { width: 165px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 22px; font-weight: bold; color: #78350f; margin-bottom: 16px; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 6px; box-shadow: 0 2px 6px rgba(120, 53, 15, 0.08); }.arch-layer-title { font-size: 13px; font-weight: bold; margin-bottom: 10px; text-align: center; }
    .arch-grid { display: grid; gap: 8px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 5px; padding: 8px; text-align: center; font-size: 11px; font-weight: 600; line-height: 1.35; color: #44220e; background: #fffcf7; border: 1px solid #d4c4a8; }.arch-box.highlight { background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%); border: 2px solid #b45309; }.arch-box.tech { font-size: 10px; color: #78350f; background: #f5efe6; }
    .arch-layer.external { background: linear-gradient(135deg, #f5efe5 0%, #ede4d4 100%); border: 2px dashed #b8a080; }.arch-layer.external .arch-layer-title { color: #8a7a68; }.arch-layer.user { background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%); border: 2px solid #d97706; }.arch-layer.user .arch-layer-title { color: #92400e; }.arch-layer.application { background: linear-gradient(135deg, #ffedd5 0%, #fdba74 100%); border: 2px solid #ea580c; }.arch-layer.application .arch-layer-title { color: #9a3412; }.arch-layer.ai { background: linear-gradient(135deg, #fee2e2 0%, #fecaca 100%); border: 2px solid #dc2626; }.arch-layer.ai .arch-layer-title { color: #991b1b; }.arch-layer.data { background: linear-gradient(135deg, #ecfdf5 0%, #d1fae5 100%); border: 2px solid #059669; }.arch-layer.data .arch-layer-title { color: #065f46; }.arch-layer.infra { background: linear-gradient(135deg, #f1f5f9 0%, #e2e8f0 100%); border: 2px solid #64748b; }.arch-layer.infra .arch-layer-title { color: #334155; }
    .arch-sidebar-panel { border-radius: 6px; padding: 10px; background: linear-gradient(135deg, #f0ead8 0%, #e5dcca 100%); border: 2px solid #c4b498; margin-bottom: 8px; box-shadow: 0 1px 3px rgba(120, 53, 15, 0.06); }.arch-sidebar-title { font-size: 12px; font-weight: bold; text-align: center; color: #78350f; margin-bottom: 6px; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #44220e; background: #fffcf7; padding: 5px; border-radius: 4px; margin: 3px 0; border: 1px solid #d4c4a8; }.arch-sidebar-item.metric { background: #fef3c7; border: 1px solid #d97706; color: #92400e; font-weight: 600; }
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
