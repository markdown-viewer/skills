# Banner + Center Layout

**Layout**: Full-width banner top/bottom + centered main layers
**Best for**: Gateway-centric architectures, user-facing systems with shared infrastructure

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-banner { padding: 14px; border: 1px solid #bbb; border-radius: 4px; background: #f5f5f5; margin-bottom: 10px; }
    .arch-banner-title { font-size: 12px; font-weight: 600; color: #555; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 10px; }
    .arch-center { }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 4px; border: 1px solid #ccc; background: #fafafa; }.arch-layer-title { font-size: 12px; font-weight: 600; color: #555; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }
  </style>
  <div class="arch-title">API Platform Architecture</div>
  <div class="arch-banner">
    <div class="arch-banner-title">Entry Points & Gateway</div>
    <div class="arch-grid arch-grid-6"><div class="arch-box">Web Client</div><div class="arch-box">Mobile SDK</div><div class="arch-box">Partner API</div><div class="arch-box highlight">API Gateway</div><div class="arch-box">Webhook Ingest</div><div class="arch-box">gRPC Endpoint</div></div>
  </div>
  <div class="arch-center">
    <div class="arch-layer">
      <div class="arch-layer-title">Auth & Identity</div>
      <div class="arch-grid arch-grid-4"><div class="arch-box">OAuth2 / OIDC</div><div class="arch-box">API Key Mgmt</div><div class="arch-box">RBAC</div><div class="arch-box">Session Store</div></div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">Core Business Services</div>
      <div class="arch-grid arch-grid-5"><div class="arch-box">User Service</div><div class="arch-box">Product Service</div><div class="arch-box">Order Service</div><div class="arch-box">Payment Service</div><div class="arch-box">Notification</div></div>
    </div>
    <div class="arch-layer">
      <div class="arch-layer-title">Data & Storage</div>
      <div class="arch-grid arch-grid-4"><div class="arch-box">Primary DB</div><div class="arch-box">Read Replicas</div><div class="arch-box">Cache Layer</div><div class="arch-box">Object Storage</div></div>
    </div>
  </div>
  <div class="arch-banner" style="margin-top: 10px;">
    <div class="arch-banner-title">Shared Platform Services</div>
    <div class="arch-grid arch-grid-6"><div class="arch-box">Container Runtime</div><div class="arch-box">Service Mesh</div><div class="arch-box">CI/CD</div><div class="arch-box">Monitoring</div><div class="arch-box">Log Aggregation</div><div class="arch-box">Secret Mgmt</div></div>
  </div>
</div>
