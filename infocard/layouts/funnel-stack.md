# Funnel Stack Layout

**Layout**: Narrowing stages from wide to narrow, progressive filtering or conversion
**Best for**: Sales funnels, conversion flows, filtering processes, recruitment pipelines, decision narrowing

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 30px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-body { margin: 0 0 20px; font-size: 15px; color: #333; }
    .card-funnel { display: flex; flex-direction: column; align-items: center; gap: 0; }
    .card-funnel-stage { display: flex; align-items: center; gap: 16px; padding: 14px 20px; border-bottom: 1px solid rgba(0,0,0,0.06); }
    .card-funnel-stage:last-child { border-bottom: none; }
    .card-funnel-bar { height: 6px; background: #111; flex-shrink: 0; }
    .card-funnel-stage:nth-child(1) .card-funnel-bar { width: 100%; }
    .card-funnel-stage:nth-child(2) .card-funnel-bar { width: 75%; }
    .card-funnel-stage:nth-child(3) .card-funnel-bar { width: 50%; }
    .card-funnel-stage:nth-child(4) .card-funnel-bar { width: 30%; }
    .card-funnel-num { font-size: 28px; font-weight: 700; color: #111; min-width: 72px; text-align: right; flex-shrink: 0; }
    .card-funnel-info { flex: 1; }
    .card-funnel-label { margin: 0 0 2px; font-size: 14px; font-weight: 700; color: #111; }
    .card-funnel-desc { margin: 0; font-size: 13px; color: #666; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Pipeline · Quarterly Review</p>
    <h1 class="card-title">Hiring Funnel Analysis</h1>
    <div class="card-bar"></div>
    <p class="card-body">End-to-end conversion from application to offer acceptance across all engineering roles, Q1 2026.</p>
    <div class="card-funnel">
      <div class="card-funnel-stage">
        <p class="card-funnel-num">1,240</p>
        <div class="card-funnel-info">
          <p class="card-funnel-label">Applications Received</p>
          <p class="card-funnel-desc">Sourced from job boards, referrals, and direct outreach. 38% referral rate.</p>
        </div>
      </div>
      <div class="card-funnel-stage">
        <p class="card-funnel-num">310</p>
        <div class="card-funnel-info">
          <p class="card-funnel-label">Phone Screens</p>
          <p class="card-funnel-desc">25% pass rate from application. Avg 22-minute call, 3-day turnaround.</p>
        </div>
      </div>
      <div class="card-funnel-stage">
        <p class="card-funnel-num">86</p>
        <div class="card-funnel-info">
          <p class="card-funnel-label">On-site Interviews</p>
          <p class="card-funnel-desc">28% advance from screen. 4-hour panel with coding, system design, and values fit.</p>
        </div>
      </div>
      <div class="card-funnel-stage">
        <p class="card-funnel-num">23</p>
        <div class="card-funnel-info">
          <p class="card-funnel-label">Offers Extended</p>
          <p class="card-funnel-desc">27% offer rate from on-site. 91% acceptance rate, 18-day avg time-to-accept.</p>
        </div>
      </div>
    </div>
    <div class="card-footer">People Operations · Q1 2026 Pipeline Report</div>
  </div>
</div>
