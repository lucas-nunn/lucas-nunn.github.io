# Wiki — lucasnunn.com (agent memory)

Agent-first project memory. Not for human consumption.

## Project

- Personal site for Lucas Nunn (cognitive neuroscience / neurofeedback)
- Single-page static site: `index.html` (GitHub Pages)
- Warm dark mono aesthetic; light theme via `prefers-color-scheme` / `data-theme`

## Active workstreams

| ID | Topic | Status |
|----|--------|--------|
| bg-2026-07 | Grainy / dynamical-systems background redesign | **shipped** Turing grain + mouse on live site |
| layout-2026-07 | Identity icons + scrollable projects feed | shipped (filters deferred) |

## Projects feed (newest → oldest visually; idx = chrono age)

| display | idx | Title | created | URL |
|---------|-----|--------|---------|-----|
| top | P03 | Beta-VAE Cortical Alignment | 2026-06-11 | https://github.com/lucas-nunn/PSM-NeuroAI-Final |
| mid | P02 | Vision-Language Brain Alignment | 2026-05-31 | https://github.com/lucas-nunn/visuo_llm_ram_rescue |
| bottom | P01 | Variational Vitro | 2026-04-26 | https://github.com/lucas-nunn/ai-sentience-scholars |

- Visual order: newest at top, oldest at bottom
- **P0x indices are chronological** (P01 = oldest), not list position — renumbered 2026-07-19 after wrong P01=top
- Display titles are human-readable (not raw repo names); README H1 used when clear
- About: "Neurosphere" links to https://neurosphere.io/ (class `inline-link`, included in blob invert hover)
- Mobile projects: `.meta` is `display:none` by default (only shown on fine-pointer hover) so invisible "GitHub ↗" no longer squeezes titles left; `.big` is `flex:1;min-width:0` and wraps

## Key files

- `index.html` — live site
- `index.html.bak` — previous canvas full-res noise grain (static)
- `demos/` — standalone background experiments for human validation
- Screenshots in repo root are design references

## Established knowledge

### Current live background (as of 2026-07-18)

- `#bg` fixed layer + `::after` radial gradient
- CSS `filter: url(#turing-dither)` — SVG `feTurbulence` + hard alpha threshold
- **Problem:** full-viewport SVG filters are extremely expensive → lag
- **Look:** stipple dither, not coherent Turing labyrinth

### Prior approach (`index.html.bak`)

- Canvas 2D `ImageData` full-resolution pixel loop with `Math.random()` grain
- Static; redraws only on resize / theme change
- Soft grain only; no dynamical structure

### Design references (repo root)

1. `Screenshot_2026-07-11_16-48-02.png` — labyrinth / maze reaction-diffusion (primary aesthetic target for "chaos / phase transitions")
2. `Screenshot_2026-07-11_16-48-09.png` — particle hourglass / light-cone
3. `Screenshot_2026-07-11_17-14-41.png` — soft site gradient baseline

### User decisions (2026-07-18)

- Visuals to demo: (1) Turing RD maze, (2) particle field, (3) soft grainy + ordered chaos hints
- Reactivity to demo: ambient-only AND subtle ambient + light mouse
- Perf: butter-smooth first (low-res GPU, cap DPR/FPS)
- Validate via standalone demos, then pick winner for `index.html`

## Conflicts

- None yet. Live site SVG dither conflicts with perf goal; demos are the resolution path.
