---
tags: [widgets, backlog, log]
---
#widgets

# Widget Build Log & Backlog

Single source of truth for the interactive widgets embedded in the book. The **status table** is the queue and current state; the **build log** below records each build with dates and deploy URLs.

Build pipeline: `engineering-widget-style` (HTML) → `obsidian-embed-artifact` (place in `widgets/<subject>/`, deploy to GitHub Pages, iframe). Base URL: `https://mrcmet.github.io/Introduction-to-Mechatronics/widgets/`.

**Status key:** `queued` (needed, not built) · `built` (HTML done, not deployed) · `deployed` (live on GitHub Pages) · `embedded ✅` (deployed *and* iframe verified on every referencing page).

## Status table

| Widget file | Referenced by | Status | Notes |
| ----------- | ------------- | ------ | ----- |
| `dynamics/grubler-mobility.html` | [[Grübler–Kutzbach Equation]], [[Mobility]] | built | HTML done 2026-08-10; iframes already in both pages; awaiting deploy/push. |
| `dynamics/four-bar-explorer.html` | [[Four-Bar Linkage]] | built | HTML done 2026-08-10; iframe already on the page; awaiting deploy/push. |

## Build log

### 2026-08-10 — `dynamics/grubler-mobility.html` (built)
- **What it does:** sliders for \(n\), \(j_1\), \(j_2\); shows \(M = 3(n-1) - 2j_1 - j_2\) live with a color-coded interpretation (M=1 drives / M=0 structure / M<0 over-constrained / M>1 multi-input). Preset buttons: four-bar, rigid triangle, bottle capper, capper+brace, five-bar.
- **Style:** built from `engineering-widget-style` base shell (KaTeX, light/dark, ≤480px responsive). No `sendPrompt` — presets are pure JS.
- **Verified:** mobility values for all five presets checked (1, 0, 1, 0, 2); tag balance clean.
- **Status:** HTML built and delivered for review. **Deploy pending** — file to land at `widgets/dynamics/grubler-mobility.html` and be pushed to GitHub Pages. The `<iframe>` is already present on both referencing pages, so it renders as soon as the file is live.

### 2026-08-10 — `dynamics/four-bar-explorer.html` (built)
- **What it does:** animated four-bar (crank–coupler–rocker–ground, Grashof crank-rocker: \(a{=}1, b{=}3.5, c{=}3.5, d{=}4\)). Slider drives the crank angle \(\theta\); coupler and rocker follow via full position analysis (circle–circle intersection). Live readouts of input \(\theta\) and output rocker angle \(\varphi\); Play button animates; toggle shows the coupler-point locus.
- **Style:** built from `engineering-widget-style` base shell; SVG blueprint figure with fixed-pivot symbols, KaTeX, light/dark, ≤480px responsive.
- **Verified:** solve assembles across all 360° (no dead points); output continuous (max 0.36°/step, no branch flip); coupler stays on the upper circuit. Tag balance clean.
- **Status:** HTML built and delivered for review. **Deploy pending** — lands at `widgets/dynamics/four-bar-explorer.html`; iframe already on the [[Four-Bar Linkage]] page.

## Notes
- When a widget deploys, flip its status to `deployed`, then to `embedded ✅` after confirming the iframe loads on every referencing page.
- This file (`_Widget Build Backlog.md`) is now both the queue and the build log — restructured 2026-08-10.
