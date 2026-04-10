# Lab Journal Style

**Style**: Academic scientific precision, off-white canvas, teal/blue pathway colors, serif authority
**Best for**: Research summaries, scientific explanations, medical content, academic papers, lab notes

## Style Characteristics

| Property | Value |
|---|---|
| Background | Lab white `#fafafa` |
| Text | Dark slate `#1e293b` |
| Accent | Teal `#0d9488` |
| Secondary | Research blue `#3b82f6` |
| Muted | Medium slate `#64748b` |
| Tint | `rgba(13,148,136,0.06)` (panel backgrounds) |
| Title Font | Georgia, `Times New Roman`, serif — weight 700 |
| Body Font | `Inter`, sans-serif |
| Texture | None — clean academic surface |
| Rules | 4px solid teal for section dividers |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #fafafa; padding: 40px; overflow: hidden; font-family: 'Inter', sans-serif; color: #1e293b; line-height: 1.6; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.15em; text-transform: uppercase; color: #64748b; }
    .card-title { margin: 0 0 16px; font-family: Georgia, 'Times New Roman', serif; font-size: 34px; font-weight: 700; line-height: 1.2; color: #1e293b; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.55; color: #475569; }
    .card-bar { width: 80px; height: 4px; margin: 0 0 20px; background: #0d9488; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.7; color: #334155; }
    .card-grid { display: grid; gap: 16px; }.card-grid-2 { grid-template-columns: 1.1fr 0.9fr; }
    .card-panel { padding: 16px 18px; background: rgba(13,148,136,0.06); border-top: 4px solid #0d9488; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #0d9488; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.6; color: #475569; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: rgba(59,130,246,0.1); color: #3b82f6; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; border: 1px solid rgba(59,130,246,0.2); }
    .card-stat { font-size: 48px; font-weight: 700; line-height: 1; color: #0d9488; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #64748b; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 700 68px/0.82 Georgia, serif; float: left; margin: 4px 12px 0 -2px; color: #0d9488; }
    .card-highlight { font-size: 17px; font-weight: 500; line-height: 1.5; color: #1e293b; padding: 10px 0 10px 18px; border-left: 4px solid #3b82f6; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #0d9488; }
    .card-divider { height: 1px; background: rgba(0,0,0,0.08); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #0d9488; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.08); font-size: 11px; color: #64748b; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Review · Circadian Biology</p>
    <h1 class="card-title">Circadian Clocks and<br>Metabolic Regulation</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">Nearly every cell in the human body contains a molecular clock — a transcription-translation feedback loop cycling with a period of approximately 24.2 hours. These peripheral oscillators, synchronized by the suprachiasmatic nucleus via light input, coordinate metabolic processes from glucose uptake to lipid oxidation.</p>
    <p class="card-highlight">Disrupted circadian rhythms increase type 2 diabetes risk by 27%</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Core Loop</p>
        <p class="card-panel-text">CLOCK:BMAL1 heterodimers activate Per and Cry transcription. PER:CRY complexes accumulate, then inhibit CLOCK:BMAL1 — completing a negative feedback cycle in ~24h.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Clinical Relevance</p>
        <p class="card-panel-text">Time-restricted eating (8–10h window) restores hepatic clock gene oscillation in mice. Shift workers show blunted cortisol rhythms and elevated HbA1c — reversible with fixed sleep schedules.</p>
      </div>
    </div>
    <span class="card-endmark">∎</span>
    <div class="card-footer">Source: Annual Review of Physiology · Vol 88 · 2026</div>
  </div>
</div>
