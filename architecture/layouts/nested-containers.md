# Nested Containers Layout

**Layout**: Concentric/nested boxes representing environment isolation
**Best for**: Cloud deployments, VPC/network topology, environment isolation

## Template

<div style="width: 1200px; box-sizing: border-box; position: relative;">
  <style scoped>
    .arch-title { text-align: center; font-size: 20px; font-weight: 600; color: #333; margin-bottom: 16px; }
    .arch-env { padding: 16px; border: 2px solid #bbb; border-radius: 6px; background: #fcfcfc; margin-bottom: 10px; }
    .arch-env-title { font-size: 13px; font-weight: 600; color: #444; margin-bottom: 12px; padding: 4px 10px; display: inline-block; border: 1px solid #ccc; border-radius: 3px; background: #f0f0f0; }
    .arch-zone-row { display: flex; gap: 12px; }
    .arch-zone { flex: 1; padding: 12px; border: 1px dashed #ccc; border-radius: 4px; background: #fafafa; }
    .arch-zone-title { font-size: 11px; font-weight: 600; color: #666; text-align: center; margin-bottom: 8px; text-transform: uppercase; letter-spacing: 0.3px; }
    .arch-grid { display: grid; gap: 6px; }.arch-grid-2 { grid-template-columns: repeat(2, 1fr); }.arch-grid-3 { grid-template-columns: repeat(3, 1fr); }
    .arch-box { border-radius: 3px; padding: 8px; text-align: center; font-size: 11px; font-weight: 500; line-height: 1.35; color: #333; background: #fff; border: 1px solid #ddd; }.arch-box.highlight { border: 2px solid #999; font-weight: 600; }
  </style>
  <div class="arch-title">Cloud Deployment Topology</div>
  <div class="arch-env">
    <div class="arch-env-title">AWS Cloud — us-east-1</div>
    <div class="arch-env">
      <div class="arch-env-title">Production VPC (10.0.0.0/16)</div>
      <div class="arch-zone-row">
        <div class="arch-zone">
          <div class="arch-zone-title">Public Subnet (AZ-a)</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box highlight">ALB</div><div class="arch-box">NAT Gateway</div><div class="arch-box">Bastion Host</div><div class="arch-box">WAF</div></div>
        </div>
        <div class="arch-zone">
          <div class="arch-zone-title">Private Subnet (AZ-a)</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">App Server 1</div><div class="arch-box">App Server 2</div><div class="arch-box">Worker Node 1</div><div class="arch-box">Worker Node 2</div></div>
        </div>
        <div class="arch-zone">
          <div class="arch-zone-title">Private Subnet (AZ-b)</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">App Server 3</div><div class="arch-box">App Server 4</div><div class="arch-box">Worker Node 3</div><div class="arch-box">Worker Node 4</div></div>
        </div>
      </div>
      <div class="arch-zone-row" style="margin-top: 10px;">
        <div class="arch-zone">
          <div class="arch-zone-title">Data Subnet (AZ-a)</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">RDS Primary</div><div class="arch-box">ElastiCache</div></div>
        </div>
        <div class="arch-zone">
          <div class="arch-zone-title">Data Subnet (AZ-b)</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">RDS Standby</div><div class="arch-box">ElastiCache Replica</div></div>
        </div>
        <div class="arch-zone">
          <div class="arch-zone-title">Shared Services</div>
          <div class="arch-grid arch-grid-2"><div class="arch-box">ECR</div><div class="arch-box">S3 Buckets</div><div class="arch-box">CloudWatch</div><div class="arch-box">Secrets Mgr</div></div>
        </div>
      </div>
    </div>
  </div>
</div>
