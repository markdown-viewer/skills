# Deep Night Style

**Style**: Cinematic dark background, atmospheric depth, glowing accent elements, high contrast
**Best for**: Entertainment, creative showcases, product reveals, evening events, gaming content

## Style Characteristics

| Property | Value |
|---|---|
| Background | Deep violet-black `#0d0d1a` |
| Text | Pure white `#f0f0f5` |
| Accent | Electric purple `#8b5cf6` |
| Secondary | Cyan glow `#06b6d4` |
| Muted | Slate `#64748b` |
| Tint | `rgba(139,92,246,0.08)` (panel backgrounds) |
| Title Font | `Inter`, sans-serif — weight 700 |
| Body Font | `Inter`, sans-serif |
| Texture | Radial gradient vignette from center |
| Rules | 3px solid electric purple with subtle glow |

## Template

<div style="max-width: 800px; box-sizing: border-box; position: relative;">
  <style scoped>
    .card-frame { max-width: 800px; }
    .card { position: relative; background: #0d0d1a; padding: 40px; overflow: hidden; font-family: 'Inter', sans-serif; color: #f0f0f5; line-height: 1.6; }
    .card::before { content: ''; position: absolute; inset: 0; pointer-events: none; background: radial-gradient(ellipse at 50% 40%, rgba(139,92,246,0.06) 0%, transparent 70%); }
    .card-meta { margin: 0 0 12px; font-size: 12px; font-weight: 700; letter-spacing: 0.18em; text-transform: uppercase; color: #64748b; }
    .card-title { margin: 0 0 16px; font-size: 36px; font-weight: 700; line-height: 1.15; letter-spacing: -0.02em; color: #f0f0f5; }
    .card-subtitle { margin: 0 0 16px; font-size: 17px; line-height: 1.55; color: #a0aec0; }
    .card-bar { width: 80px; height: 3px; margin: 0 0 20px; background: #8b5cf6; box-shadow: 0 0 10px rgba(139,92,246,0.4); }
    .card-body { margin: 0 0 16px; font-size: 15px; line-height: 1.6; color: #cbd5e1; }
    .card-grid { display: grid; gap: 16px; }.card-grid-2 { grid-template-columns: 1.1fr 0.9fr; }
    .card-panel { padding: 16px 18px; background: rgba(139,92,246,0.08); border-top: 3px solid #8b5cf6; }
    .card-panel-title { margin: 0 0 8px; font-size: 12px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: #8b5cf6; }
    .card-panel-text { margin: 0; font-size: 14px; line-height: 1.55; color: #a0aec0; }
    .card-tag { display: inline-block; font-size: 11px; font-weight: 600; padding: 2px 8px; background: rgba(139,92,246,0.2); color: #a78bfa; margin-right: 6px; margin-bottom: 4px; letter-spacing: 0.05em; border: 1px solid rgba(139,92,246,0.3); }
    .card-stat { font-size: 48px; font-weight: 700; line-height: 1; color: #06b6d4; margin: 0; text-shadow: 0 0 16px rgba(6,182,212,0.3); }
    .card-stat-label { font-size: 12px; font-weight: 600; color: #64748b; text-transform: uppercase; letter-spacing: 0.1em; margin: 4px 0 0; }
    .card-body.dropcap::first-letter { font: 700 72px/0.82 Georgia, serif; float: left; margin: 4px 12px 0 -2px; color: #8b5cf6; }
    .card-highlight { font-size: 17px; font-weight: 500; line-height: 1.5; color: #f0f0f5; padding: 10px 0 10px 18px; border-left: 3px solid #06b6d4; margin: 16px 0; }
    .card-item { margin-bottom: 14px; }.card-item:last-child { margin-bottom: 0; }
    .card-item-label { margin: 0 0 4px; font-size: 15px; font-weight: 600; color: #06b6d4; }
    .card-divider { height: 1px; background: rgba(139,92,246,0.2); margin: 20px 0; }
    .card-endmark { display: block; text-align: right; font-size: 14px; color: #8b5cf6; opacity: 0.3; margin-top: 20px; }
    .card-footer { margin-top: 20px; padding-top: 12px; border-top: 1px solid rgba(139,92,246,0.15); font-size: 11px; color: #64748b; letter-spacing: 0.05em; }
  </style>
  <div class="card">
    <p class="card-meta">Feature Spotlight · Immersive Audio</p>
    <h1 class="card-title">Spatial Sound Engine:<br>Beyond Stereo</h1>
    <div class="card-bar"></div>
    <p class="card-body dropcap">The next frontier of audio rendering places the listener inside a three-dimensional sound field. Using head-related transfer functions and real-time ray tracing, each sound source is positioned in virtual space with sub-millimeter precision — creating presence that headphones alone could never achieve.</p>
    <p class="card-highlight">128 simultaneous sound sources, sub-2ms latency</p>
    <div class="card-grid card-grid-2">
      <div class="card-panel">
        <p class="card-panel-title">Core Technology</p>
        <p class="card-panel-text">Ambisonics rendering · HRTF personalization via ear photos · Room impulse response modeling · Dynamic occlusion and diffraction</p>
      </div>
      <div class="card-panel">
        <p class="card-panel-title">Applications</p>
        <p class="card-panel-text">Open-world game environments · Virtual concert halls · Architectural acoustics preview · Therapeutic sound environments</p>
      </div>
    </div>
    <span class="card-endmark">✧</span>
    <div class="card-footer">Audio R&D Division · Technical Preview · 2026</div>
  </div>
</div>
