# Project Webpage — Stepwise-Flow-GRPO

**Live site**: https://stepwiseflowgrpo.com
**GitHub repo**: `yashsavani/stepwiseflowgrpo.com` (GitHub Pages, main branch, root `/`)

## Structure

- `index.html` — Single self-contained HTML file; no build step, no external dependencies, no JS frameworks
- `CNAME` — Sets custom domain to `stepwiseflowgrpo.com` for GitHub Pages
- `static/` — PNG renders of paper figures (generated from PDFs via `pdftoppm -png -r 300`)

## Static Assets (`static/`)

| File | Description |
|------|-------------|
| `teaser_pdf.png` | Main teaser figure (used in header section) |
| `method.png` | Method overview diagram |
| `qualitative.png` | Qualitative comparison (Flow-GRPO vs ours) |
| `qual-1.png`, `qual-2.png`, `qual-3.png` | Extended qualitative results (3 pages) |
| `more_images.png` | Comparison across training objectives |
| `pickscore_flowsde.png` | PickScore reward vs. training steps |
| `imagereward_flowsde.png` | ImageReward reward vs. training steps |
| `unified_flowsde.png` | UnifiedReward reward vs. training steps |
| `picskscoreds_steps.png` | PickScore dataset reward vs. training steps |
| `pickscore_flowsde_time.png` | PickScore reward vs. wall-clock time |
| `imagereward_flowsde_time.png` | ImageReward reward vs. wall-clock time |
| `unified_flowsde_time.png` | UnifiedReward reward vs. wall-clock time |
| `picskscoreds_runtime.png` | PickScore dataset reward vs. wall-clock time |
| `geneval_runtime.png` | Extended 400 GPU-hour GenEval training result |
| `bettersde.png` | DDIM-inspired SDE comparison figure |
| `gain_magnitudes.png` | Gain magnitude analysis figure |

## Webpage Sections (in order)

1. **Header** — Title, venue badge (CVPR 2026), authors, affiliations, arXiv link
2. **Teaser** — `teaser_pdf.png` with caption explaining stepwise credit assignment
3. **Abstract** — Paper abstract
4. **Key Results** — Highlight cards (0.87 GenEval score, 3/4 settings superior efficiency)
5. **Sample Efficiency** — 4-column grid of reward-vs-steps plots
6. **Wall-Clock Efficiency** — 4-column grid of reward-vs-time plots
7. **Extended Training** — `geneval_runtime.png` showing 400 GPU-hr result
8. **GenEval Benchmark** — Full results table with all models and subtasks
9. **Qualitative Results** — `qualitative.png` comparison
10. **More Results** — `qual-1/2/3.png` and `more_images.png`
11. **BibTeX** — Citation block with copy button

## Styling Conventions

- All CSS is inline in `index.html` using CSS custom properties (`--bg`, `--text`, `--accent`, etc.)
- Dark mode via `@media (prefers-color-scheme: dark)` — override the `:root` variables in the dark block
- Max content width: 900px (controlled by `--max-width`)
- Figure grids: `.figure-grid` (4-col), `.figure-grid-2` (2-col); collapse to 2-col on mobile (<600px)
- Highlighted table rows use class `highlight` (bold, accent color); section dividers use `table-section`

## Deployment

- Hosted on GitHub Pages from the `yashsavani/stepwiseflowgrpo.com` repo (main branch, root `/`)
- Custom domain: `stepwiseflowgrpo.com` (HTTPS enforced)
- DNS: A records pointing to GitHub Pages IPs; `www` CNAME → `stepwiseflowgrpo.com`
- No CI/CD — push to main deploys automatically via GitHub Pages
- To add a new figure: add PNG to `static/`, reference as `static/filename.png` in `index.html`
