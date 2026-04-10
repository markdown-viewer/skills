# Timeline Flow Layout

**Layout**: Vertical sequential flow with connected steps and directional progression
**Best for**: Processes, timelines, tutorials, step-by-step guides, historical chronology

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card { position: relative; background: #fafafa; padding: 40px; font-family: sans-serif; color: #111; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #888; }
    .card-title { margin: 0 0 14px; font-size: 30px; font-weight: 700; line-height: 1.2; color: #111; }
    .card-bar { width: 80px; height: 6px; margin: 0 0 20px; background: #111; }
    .card-subtitle { margin: 0 0 24px; font-size: 15px; line-height: 1.55; color: #444; }
    .card-timeline { position: relative; padding-left: 32px; }
    .card-timeline::before { content: ''; position: absolute; left: 8px; top: 4px; bottom: 4px; width: 2px; background: rgba(0,0,0,0.12); }
    .card-step { position: relative; margin-bottom: 24px; }
    .card-step:last-child { margin-bottom: 0; }
    .card-step-dot { position: absolute; left: -32px; top: 2px; width: 18px; height: 18px; border-radius: 50%; background: #111; display: flex; align-items: center; justify-content: center; font-size: 9px; font-weight: 700; color: #fafafa; }
    .card-step-dot.active { background: #333; box-shadow: 0 0 0 3px rgba(0,0,0,0.08); }
    .card-step-title { margin: 0 0 4px; font-size: 15px; font-weight: 700; color: #111; }
    .card-step-text { margin: 0; font-size: 13px; line-height: 1.55; color: #555; }
    .card-footer { margin-top: 24px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.1); font-size: 11px; color: #999; }
  </style>
  <div class="card">
    <p class="card-meta">Process · Tutorial</p>
    <h1 class="card-title">Project Delivery Flow</h1>
    <div class="card-bar"></div>
    <p class="card-subtitle">A clear four-step process from discovery to launch, ensuring quality at every stage.</p>
    <div class="card-timeline">
      <div class="card-step">
        <div class="card-step-dot">1</div>
        <p class="card-step-title">Discovery & Research</p>
        <p class="card-step-text">Interview stakeholders, audit existing systems, and define success metrics. Output: requirements document.</p>
      </div>
      <div class="card-step">
        <div class="card-step-dot active">2</div>
        <p class="card-step-title">Design & Prototype</p>
        <p class="card-step-text">Create wireframes, test with users, iterate on feedback. Build a clickable prototype for validation.</p>
      </div>
      <div class="card-step">
        <div class="card-step-dot">3</div>
        <p class="card-step-title">Build & Test</p>
        <p class="card-step-text">Develop in sprints with continuous testing. Automated CI/CD pipeline ensures quality gates at every commit.</p>
      </div>
      <div class="card-step">
        <div class="card-step-dot">4</div>
        <p class="card-step-title">Launch & Monitor</p>
        <p class="card-step-text">Staged rollout with feature flags. Real-time monitoring for performance, errors, and user engagement.</p>
      </div>
    </div>
    <div class="card-footer">Methodology · Agile Delivery Framework</div>
  </div>
</div>
