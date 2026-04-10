# Soft Neutral Style

**Style**: Warm white background, gentle earth tones, rounded elements, relaxed spacing, approachable
**Best for**: Lifestyle content, wellness, education, gentle branding

## Style Characteristics

| Property | Value |
|---|---|
| Background | Warm white `#faf9f7` |
| Text | Warm dark `#2d2a26` |
| Accent | Terracotta `#c2785c` (rules, tags) |
| Muted | Warm gray `#8a8279` (meta, captions) |
| Tint | `rgba(194,120,92,0.08)` (panel backgrounds) |
| Title Font | `Noto Serif SC`, serif — weight 700 |
| Body Font | `Inter`, `Noto Sans SC`, sans-serif |
| Rules | 4px solid accent terracotta |
| Radius | 6px on panels |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #faf9f7; padding: 40px; overflow: hidden; font-family: 'Inter', 'Noto Sans SC', sans-serif; color: #2d2a26; line-height: 1.65; border-radius: 8px; }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 600; letter-spacing: 0.12em; text-transform: uppercase; color: #c2785c; }
    .card-title { margin: 0 0 14px; font-family: 'Noto Serif SC', serif; font-size: 32px; font-weight: 700; line-height: 1.25; color: #2d2a26; }
    .card-subtitle { margin: 0 0 16px; font-size: 16px; line-height: 1.65; color: #5c564e; }
    .card-bar { width: 60px; height: 4px; margin: 0 0 20px; background: #c2785c; border-radius: 2px; }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.65; color: #3d3832; }
    .card-grid { display: grid; gap: 14px; }.card-grid-2 { grid-template-columns: 1fr 1fr; }
    .card-panel { padding: 16px 18px; background: rgba(194,120,92,0.08); border-top: 4px solid #c2785c; border-radius: 0 0 6px 6px; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: #c2785c; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.6; color: #5c564e; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 3px 10px; background: rgba(194,120,92,0.15); color: #a0614a; border-radius: 12px; margin-right: 6px; margin-bottom: 4px; }
    .card-stat { font-size: 44px; font-weight: 700; line-height: 1; color: #c2785c; margin: 0; }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #8a8279; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 700 64px/0.82 'Noto Serif SC', Georgia, serif; float: left; margin: 4px 12px 0 -2px; color: #c2785c; }
    .card-highlight { font-size: 16px; font-weight: 500; line-height: 1.5; color: #2d2a26; padding: 10px 0 10px 16px; border-left: 3px solid #c2785c; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #2d2a26; }
    .card-divider { height: 1px; background: rgba(0,0,0,0.08); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #c2785c; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(0,0,0,0.08); font-size: 11px; color: #8a8279; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Wellness · Sleep Science</p>
    <h1 class="card-title">The Architecture of<br>Restorative Sleep</h1>
    <div class="card-bar"></div>
    <p class="card-subtitle">Sleep is not a passive state but an active cycle of neural maintenance. Each 90-minute cycle alternates between light, deep, and REM stages — each serving a distinct biological purpose.</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Deep Sleep</p>
        <p class="card-panel-text">Occurs primarily in the first half of the night. The body releases growth hormone, repairs tissue, and the glymphatic system clears metabolic waste from the brain.</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">REM Sleep</p>
        <p class="card-panel-text">Dominates the final hours before waking. Emotional memories are processed, creative connections form, and motor learning consolidates. Adults need 90–120 minutes per night.</p>
      </div>
    </div>
    <div class="card-footer">Adapted from Why We Sleep · Matthew Walker · 2017</div>
  </div>
</div>
