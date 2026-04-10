# Stark Block Style

**Style**: High-saturation solid fills, 3px black borders, 0px radius (sharp corners), offset shadow, maximum contrast
**Best for**: Creative studios, education platforms, indie developers, tech blogs

## Style Characteristics

| Property | Value |
|---|---|
| Fill | High-saturation solid colors, no gradients |
| Border | 3px solid black (#000) |
| Radius | 0px — sharp corners everywhere |
| Shadow | `4px 4px 0 #000` offset block shadow |
| Text | Black (#000) on bright backgrounds |
| Palette | Bright yellow / Hot pink / Electric blue / Lime / Lavender |

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative; background: #fffef5; padding: 20px;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 14px; }.arch-sidebar { width: 165px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 24px; font-weight: 900; color: #000000; margin-bottom: 18px; text-transform: uppercase; letter-spacing: 2px; }
    .arch-layer { margin: 10px 0; padding: 14px; border-radius: 0; border: 3px solid #000; box-shadow: 5px 5px 0 #000; }.arch-layer-title { font-size: 14px; font-weight: 900; color: #000; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 1px; }
    .arch-grid { display: grid; gap: 8px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 0; padding: 8px; text-align: center; font-size: 11px; font-weight: 700; line-height: 1.35; color: #000; background: #ffffff; border: 2px solid #000; box-shadow: 3px 3px 0 #000; }.arch-box.highlight { background: #facc15; border: 3px solid #000; }.arch-box.tech { font-size: 10px; background: #f5f5f0; }
    .arch-layer.external { background: #e5e5e0; border-style: dashed; }.arch-layer.external .arch-layer-title { color: #000; }.arch-layer.user { background: #a5d8ff; }.arch-layer.user .arch-layer-title { color: #000; }.arch-layer.application { background: #ffec99; }.arch-layer.application .arch-layer-title { color: #000; }.arch-layer.ai { background: #b2f2bb; }.arch-layer.ai .arch-layer-title { color: #000; }.arch-layer.data { background: #fcc2d7; }.arch-layer.data .arch-layer-title { color: #000; }.arch-layer.infra { background: #d0bfff; }.arch-layer.infra .arch-layer-title { color: #000; }
    .arch-sidebar-panel { border-radius: 0; padding: 10px; background: #f0f0eb; border: 3px solid #000; box-shadow: 4px 4px 0 #000; margin-bottom: 10px; }.arch-sidebar-title { font-size: 12px; font-weight: 900; text-align: center; color: #000; margin-bottom: 6px; text-transform: uppercase; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #000; background: #fff; padding: 5px; border-radius: 0; margin: 3px 0; border: 1.5px solid #000; }.arch-sidebar-item.metric { background: #b2f2bb; border: 2px solid #000; font-weight: 700; }
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
