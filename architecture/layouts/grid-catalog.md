# Grid Catalog Layout

**Layout**: Equal-weight cards in a uniform grid
**Best for**: Service catalogs, component libraries, equal-weight microservices

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-catalog { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; }
    .arch-card { border: 1px solid #ccc; border-radius: 4px; padding: 14px; background: #fafafa; }
    .arch-card-title { font-size: 12px; font-weight: 600; color: #555; text-align: center; text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 10px; padding-bottom: 6px; border-bottom: 1px solid #ddd; }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; margin: 4px 0; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }
  </style>
  <div class="arch-title">Microservices Catalog</div>
  <div class="arch-catalog">
    <div class="arch-card">
      <div class="arch-card-title">User Service</div>
      <div class="arch-box">Registration</div>
      <div class="arch-box">Authentication</div>
      <div class="arch-box">Profile Mgmt</div>
      <div class="arch-box">Preferences</div>
    </div>
    <div class="arch-card">
      <div class="arch-card-title">Order Service</div>
      <div class="arch-box highlight">Order Processing</div>
      <div class="arch-box">Cart Management</div>
      <div class="arch-box">Order History</div>
      <div class="arch-box">Returns</div>
    </div>
    <div class="arch-card">
      <div class="arch-card-title">Payment Service</div>
      <div class="arch-box">Card Processing</div>
      <div class="arch-box">Invoicing</div>
      <div class="arch-box">Refunds</div>
      <div class="arch-box">Subscriptions</div>
    </div>
    <div class="arch-card">
      <div class="arch-card-title">Notification</div>
      <div class="arch-box">Email</div>
      <div class="arch-box">SMS</div>
      <div class="arch-box">Push</div>
      <div class="arch-box">In-App</div>
    </div>
    <div class="arch-card">
      <div class="arch-card-title">Inventory</div>
      <div class="arch-box">Stock Tracking</div>
      <div class="arch-box">Warehouse</div>
      <div class="arch-box">Suppliers</div>
      <div class="arch-box">Forecasting</div>
    </div>
    <div class="arch-card">
      <div class="arch-card-title">Search Service</div>
      <div class="arch-box">Full-Text Search</div>
      <div class="arch-box">Autocomplete</div>
      <div class="arch-box">Faceted Filter</div>
      <div class="arch-box">Ranking</div>
    </div>
    <div class="arch-card">
      <div class="arch-card-title">Analytics</div>
      <div class="arch-box">Event Tracking</div>
      <div class="arch-box">Funnel Analysis</div>
      <div class="arch-box">A/B Testing</div>
      <div class="arch-box">Reporting</div>
    </div>
    <div class="arch-card">
      <div class="arch-card-title">Media Service</div>
      <div class="arch-box">Upload</div>
      <div class="arch-box">Processing</div>
      <div class="arch-box">CDN Delivery</div>
      <div class="arch-box">Thumbnails</div>
    </div>
  </div>
</div>
