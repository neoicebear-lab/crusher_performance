# Crusher Performance Dashboard

Interactive executive dashboard for Hongsa Power Coal Handling System — monitors 4 crushers (CR1–CR4), throughput, stock balance, and sulfur blending quality.

**Live demo:** Enable GitHub Pages on this repo (see steps below) and open the published URL.

---

## Features

- 6 executive KPI cards (Coal Crushed, Coal Out, Stock Balance, Operating Days, Fleet Utilization, Sulfur Blend)
- Per-crusher status with utilization progress bars and traffic-light indicators
- Daily performance trend chart (filterable: YTD / 30D / 7D)
- Monthly coal throughput (in vs out)
- Average performance vs target per crusher
- Sulfur blending vs 0.7% target
- Single-page responsive layout — no scrolling required

---

## Deploy to GitHub Pages (3 steps)

### Option A — Drag & drop (easiest)

1. Create a new public repository on GitHub (e.g. `crusher-dashboard`).
2. On the empty repo page, click **uploading an existing file** and drag both `index.html` and `.nojekyll` into the browser. Commit.
3. Go to **Settings → Pages**, set **Source = `main` branch / root**, save.
4. Wait ~1 minute → your dashboard is live at:
   `https://<your-username>.github.io/crusher-dashboard/`

### Option B — Git CLI

```bash
git init
git add index.html .nojekyll README.md
git commit -m "Initial dashboard"
git branch -M main
git remote add origin https://github.com/<your-username>/crusher-dashboard.git
git push -u origin main
```

Then enable Pages in **Settings → Pages → Source: main / root**.

---

## File contents

| File | Purpose |
|------|---------|
| `index.html` | The dashboard (self-contained — Chart.js loaded from CDN) |
| `.nojekyll` | Tells GitHub Pages to skip Jekyll processing |
| `README.md` | This file |

---

## Updating the data

The dashboard data is embedded as a JavaScript object inside `index.html` (look for `const DATA = {...}`). To refresh:

1. Open the source spreadsheet (`Data_Dashboard.xlsx`)
2. Re-export the aggregated values
3. Replace the `DATA` object in `index.html`
4. Commit and push — GitHub Pages auto-redeploys in ~1 minute

---

*Hongsa Power Co., Ltd. — Coal Operation*
