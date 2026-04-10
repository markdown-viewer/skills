# Hub & Spoke Layout

**Layout**: Central hub with satellite nodes radiating outward
**Best for**: Integration platforms, API hubs, event-driven architectures, ESB patterns

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-hub-layout { display: flex; flex-direction: column; align-items: center; gap: 10px; }
    .arch-hub-row { display: flex; gap: 10px; align-items: stretch; width: 100%; }
    .arch-hub { flex: 1; border: 2px solid #999; border-radius: 6px; padding: 20px; background: #f5f5f5; text-align: center; }
    .arch-hub-title { font-size: 14px; font-weight: 700; color: #333; margin-bottom: 10px; text-transform: uppercase; }
    .arch-spoke { flex: 1; border: 1px solid #ccc; border-radius: 4px; padding: 14px; background: #fafafa; }
    .arch-spoke-title { font-size: 12px; font-weight: 600; color: #555; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 10px; padding-bottom: 6px; border-bottom: 1px solid #ddd; }
    .arch-connector { text-align: center; font-size: 18px; color: #999; padding: 2px 0; }.arch-connector-h { display: flex; align-items: center; justify-content: center; width: 36px; flex-shrink: 0; font-size: 20px; color: #999; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }
  </style>
  <div class="arch-title">Integration Platform</div>
  <div class="arch-hub-layout">
    <div class="arch-hub-row">
      <div class="arch-spoke">
        <div class="arch-spoke-title">CRM Domain</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Salesforce</div><div class="arch-box">HubSpot</div><div class="arch-box">Contact Sync</div><div class="arch-box">Lead Scoring</div></div>
      </div>
      <div class="arch-spoke">
        <div class="arch-spoke-title">E-Commerce</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Product Catalog</div><div class="arch-box">Order Mgmt</div><div class="arch-box">Inventory</div><div class="arch-box">Pricing</div></div>
      </div>
    </div>
    <div class="arch-connector">↕</div>
    <div class="arch-hub-row">
      <div class="arch-spoke">
        <div class="arch-spoke-title">Marketing</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Campaigns</div><div class="arch-box">Email Automation</div><div class="arch-box">Segmentation</div><div class="arch-box">Attribution</div></div>
      </div>
      <div class="arch-connector-h">↔</div>
      <div class="arch-hub">
        <div class="arch-hub-title">Integration Hub</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box highlight">Event Bus</div><div class="arch-box highlight">API Router</div><div class="arch-box">Schema Registry</div><div class="arch-box">Transform Engine</div><div class="arch-box">Rate Limiter</div><div class="arch-box">Retry Queue</div></div>
      </div>
      <div class="arch-connector-h">↔</div>
      <div class="arch-spoke">
        <div class="arch-spoke-title">Support</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Helpdesk</div><div class="arch-box">Ticketing</div><div class="arch-box">Knowledge Base</div><div class="arch-box">Live Chat</div></div>
      </div>
    </div>
    <div class="arch-connector">↕</div>
    <div class="arch-hub-row">
      <div class="arch-spoke">
        <div class="arch-spoke-title">Finance</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">ERP</div><div class="arch-box">Invoicing</div><div class="arch-box">Tax Engine</div><div class="arch-box">Reporting</div></div>
      </div>
      <div class="arch-spoke">
        <div class="arch-spoke-title">Logistics</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Warehouse</div><div class="arch-box">Shipping</div><div class="arch-box">Tracking</div><div class="arch-box">Returns</div></div>
      </div>
      <div class="arch-spoke">
        <div class="arch-spoke-title">Analytics</div>
        <div class="arch-grid arch-grid-2"><div class="arch-box">Data Lake</div><div class="arch-box">BI Tools</div><div class="arch-box">ML Pipeline</div><div class="arch-box">Dashboards</div></div>
      </div>
    </div>
  </div>
</div>
