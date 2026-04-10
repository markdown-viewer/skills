# Right Sidebar Layout

**Layout**: Main content area + right sidebar
**Best for**: Systems with security/compliance emphasis, governance-focused views

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-wrapper { display: flex; gap: 12px; }.arch-sidebar { width: 180px; flex-shrink: 0; }.arch-main { flex: 1; min-width: 0; }.arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-layer { margin: 8px 0; padding: 14px; border-radius: 4px; border: 1px solid #ccc; background: #fafafa; }.arch-layer-title { font-size: 12px; font-weight: 600; color: #555; margin-bottom: 10px; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }.arch-grid-4 { grid-template-columns: repeat(4, 1fr); }.arch-grid-5 { grid-template-columns: repeat(5, 1fr); }.arch-grid-6 { grid-template-columns: repeat(6, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }.arch-box.tech { font-size: 10px; color: #666; }
    .arch-sidebar-panel { border-radius: 4px; padding: 10px; background: #fafafa; border: 1px solid #ccc; margin-bottom: 8px; }.arch-sidebar-title { font-size: 11px; font-weight: 600; text-align: center; color: #555; margin-bottom: 6px; text-transform: uppercase; letter-spacing: 0.3px; }.arch-sidebar-item { font-size: 10px; text-align: center; color: #666; background: #fff; padding: 4px; border-radius: 3px; margin: 3px 0; border: 1px solid #eee; }
  </style>
  <div class="arch-title">Enterprise Architecture</div>
  <div class="arch-wrapper">
    <div class="arch-main">
      <div class="arch-layer">
        <div class="arch-layer-title">User Access Layer</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Web Portal</div><div class="arch-box">Mobile App</div><div class="arch-box">Partner API</div><div class="arch-box">Admin Dashboard</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Application Layer</div>
        <div class="arch-grid arch-grid-3"><div class="arch-box highlight">Core Platform</div><div class="arch-box">Integration Hub</div><div class="arch-box">Workflow Engine</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Domain Services</div>
        <div class="arch-grid arch-grid-5"><div class="arch-box">Customer Mgmt</div><div class="arch-box">Order Processing</div><div class="arch-box">Inventory</div><div class="arch-box">Payments</div><div class="arch-box">Shipping</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Data Platform</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">OLTP Database</div><div class="arch-box">Data Warehouse</div><div class="arch-box">Data Lake</div><div class="arch-box">Cache Layer</div></div>
      </div>
      <div class="arch-layer">
        <div class="arch-layer-title">Infrastructure</div>
        <div class="arch-grid arch-grid-4"><div class="arch-box">Cloud Platform</div><div class="arch-box">Networking</div><div class="arch-box">Container Runtime</div><div class="arch-box">Observability</div></div>
      </div>
    </div>
    <div class="arch-sidebar">
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Security</div><div class="arch-sidebar-item">IAM / SSO</div><div class="arch-sidebar-item">mTLS / Encryption</div><div class="arch-sidebar-item">WAF / DDoS</div><div class="arch-sidebar-item">Secret Management</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Compliance</div><div class="arch-sidebar-item">GDPR</div><div class="arch-sidebar-item">SOC 2</div><div class="arch-sidebar-item">PCI DSS</div><div class="arch-sidebar-item">Audit Trail</div></div>
      <div class="arch-sidebar-panel"><div class="arch-sidebar-title">Governance</div><div class="arch-sidebar-item">API Standards</div><div class="arch-sidebar-item">Data Catalog</div><div class="arch-sidebar-item">Cost Management</div></div>
    </div>
  </div>
</div>
