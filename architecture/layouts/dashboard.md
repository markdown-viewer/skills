# Dashboard Layout

**Layout**: Top KPI row + multi-panel grid below
**Best for**: System overviews with KPIs, monitoring dashboards, executive summaries

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-kpi-row { display: flex; gap: 10px; margin-bottom: 14px; }
    .arch-kpi { flex: 1; border: 1px solid #ccc; border-radius: 4px; padding: 12px; text-align: center; background: #fafafa; }
    .arch-kpi-value { font-size: 20px; font-weight: 700; color: #333; }.arch-kpi-label { font-size: 10px; color: #777; text-transform: uppercase; letter-spacing: 0.5px; margin-top: 4px; }
    .arch-panels-row { display: flex; gap: 10px; margin-bottom: 10px; }
    .arch-panel { flex: 1; border: 1px solid #ccc; border-radius: 4px; padding: 14px; background: #fafafa; }
    .arch-panel-title { font-size: 12px; font-weight: 600; color: #555; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }
  </style>
  <div class="arch-title">System Dashboard</div>
  <div class="arch-kpi-row">
    <div class="arch-kpi"><div class="arch-kpi-value">99.9%</div><div class="arch-kpi-label">Uptime</div></div>
    <div class="arch-kpi"><div class="arch-kpi-value">142ms</div><div class="arch-kpi-label">Avg Latency</div></div>
    <div class="arch-kpi"><div class="arch-kpi-value">2.4M</div><div class="arch-kpi-label">Daily Requests</div></div>
    <div class="arch-kpi"><div class="arch-kpi-value">12</div><div class="arch-kpi-label">Active Services</div></div>
    <div class="arch-kpi"><div class="arch-kpi-value">3</div><div class="arch-kpi-label">Regions</div></div>
  </div>
  <div class="arch-panels-row">
    <div class="arch-panel">
      <div class="arch-panel-title">Frontend Services</div>
      <div class="arch-grid arch-grid-2"><div class="arch-box">Web App</div><div class="arch-box">Mobile App</div><div class="arch-box">Admin Portal</div><div class="arch-box">API Docs</div></div>
    </div>
    <div class="arch-panel">
      <div class="arch-panel-title">Backend Services</div>
      <div class="arch-grid arch-grid-3"><div class="arch-box highlight">API Gateway</div><div class="arch-box">Auth Service</div><div class="arch-box">User Service</div><div class="arch-box">Order Service</div><div class="arch-box">Payment</div><div class="arch-box">Notification</div></div>
    </div>
  </div>
  <div class="arch-panels-row">
    <div class="arch-panel">
      <div class="arch-panel-title">Data Stores</div>
      <div class="arch-grid arch-grid-2"><div class="arch-box">PostgreSQL</div><div class="arch-box">Redis</div><div class="arch-box">Elasticsearch</div><div class="arch-box">S3</div></div>
    </div>
    <div class="arch-panel">
      <div class="arch-panel-title">Infrastructure</div>
      <div class="arch-grid arch-grid-2"><div class="arch-box">Kubernetes</div><div class="arch-box">Terraform</div><div class="arch-box">Prometheus</div><div class="arch-box">Grafana</div></div>
    </div>
    <div class="arch-panel">
      <div class="arch-panel-title">External</div>
      <div class="arch-grid arch-grid-2"><div class="arch-box">Stripe</div><div class="arch-box">SendGrid</div><div class="arch-box">Auth0</div><div class="arch-box">Cloudflare</div></div>
    </div>
  </div>
</div>
