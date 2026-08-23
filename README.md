# Plasma Atlas

An interactive map of **273 hand-built physics visualizers** — fusion, plasma, gyrokinetics,
electromagnetism, quantum, nuclear, relativity, vector calculus and a few life-science explainers —
filed into one browsable constellation.

Every bubble is a self-contained HTML page. Click one, read the card, hit **Open full** and it runs —
no build step, no server, no internet required beyond the page itself.

## What's in here

| | |
|---|---|
| Visualizers | 273 (287 files including earlier versions) |
| Fields | 13 |
| Span | Dec 2025 → Aug 2026 |
| Size | ~21 MB |

**Fields:** Fusion Machines · Equilibrium & Geometry · Gyrokinetics & Turbulence ·
Kinetic Theory & Vlasov · Plasma Fundamentals · Electromagnetism · Quantum & Particles ·
Nuclear & Radiation · Relativity & Cosmos · Math & Vector Calculus · Motion & Mechanics ·
Life Sciences · Applied & Everyday

## Using it

- **Drag** to pan, **scroll** to zoom, **click** a bubble to open its card
- **Drag a bubble** to shove it around — the cluster settles back
- **▶ Play** runs the whole collection as a timeline: bubbles ignite on the day they were built,
  and a thread is drawn from each one back to the page it grew out of. Solid threads are pages
  made in the same sitting; dashed threads reach back to an earlier one it echoes. Scrub the
  track, change speed, or `✕` to leave.
- Click a field chip in the left rail to isolate it; click again to bring everything back
- **`/`** search · **`space`** play/pause · **`g`** map ↔ grid · **`Esc`** back out
- Every card deep-links: `index.html#<id>` reopens straight to that visualizer

## Publishing to GitHub Pages

```bash
cd plasma-atlas
git init
git add -A
git commit -m "Plasma Atlas"
git branch -M main
git remote add origin git@github.com:<you>/plasma-atlas.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Source: Deploy from a branch → `main` / `(root)`**.
It goes live at `https://<you>.github.io/plasma-atlas/` in a minute or two.

> The `.nojekyll` file in the root is **required** — without it GitHub Pages runs Jekyll,
> which silently drops the `_lib/` directory (leading underscore), and every page that
> renders equations loses its MathJax.

The repo is ~21 MB, comfortably inside GitHub's limits.

## Layout

```
plasma-atlas/
├── index.html                    the atlas (self-contained, no dependencies)
├── .nojekyll                     keeps GitHub Pages from eating _lib/
├── _lib/                         MathJax, KaTeX, React — shared by the pages
└── <date>_<topic>/               one folder per source session
    └── *.html                    the visualizers themselves
```
