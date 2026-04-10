# Single Stack Layout

**Layout**: Full-width vertical layers, no sidebars
**Best for**: Simple services, microservice detail views, focused documentation

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-main { width: 100%; }.arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 4px; border: 1px solid #ccc; background: #fafafa; }.arch-layer-title { font-size: 12px; font-weight: 600; color: #555; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }.arch-box.tech { font-size: 10px; color: #666; }
  </style>
  <div class="arch-title">Service Architecture</div>
  <div class="arch-main">
    <div class="arch-layer">
      <div class="arch-layer-title">Presentation Layer</div>
      <div class="arch-grid arch-grid-5"><div class="arch-box">Web App</div><div class="arch-box">Mobile App</div><div class="arch-box">Admin Console</div><div class="arch-box">API Portal</div><div class="arch-box">CLI Tool</div></div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">API Gateway</div>
      <div class="arch-grid arch-grid-6"><div class="arch-box">Routing</div><div class="arch-box highlight">Auth</div><div class="arch-box">Rate Limiting</div><div class="arch-box">Caching</div><div class="arch-box">Logging</div><div class="arch-box">Transformation</div></div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">Business Services</div>
      <div class="arch-grid arch-grid-4"><div class="arch-box">User Service</div><div class="arch-box">Order Service</div><div class="arch-box">Payment Service</div><div class="arch-box">Notification Service</div></div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">Data Layer</div>
      <div class="arch-grid arch-grid-5"><div class="arch-box">PostgreSQL</div><div class="arch-box">Redis</div><div class="arch-box">Elasticsearch</div><div class="arch-box">S3</div><div class="arch-box">Kafka</div></div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">Infrastructure</div>
      <div class="arch-grid arch-grid-4"><div class="arch-box">Kubernetes</div><div class="arch-box">Terraform</div><div class="arch-box">Prometheus</div><div class="arch-box">Grafana</div></div>
    </div>
  </div>
</div>
