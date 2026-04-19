# Grüns — Signal Desk

A consumer sentiment & demand forecasting dashboard built as a sample product for Grüns. Two pages:

- **`/` (index.html)** — the Signal Desk itself: leading indicators, cohort retention, competitor substitution mapping, 60-day forecast with driver attribution, SKU telemetry
- **`/integrity` (integrity.html)** — the robustness audit: 24-test suite across sampling, measurement, model, drift, coverage, and reproducibility dimensions; backtest MAE; confusion matrix for social listening; drift monitor; known caveats

Built as a single-file-per-page static site — no framework, no build step, renders in any browser.

---

## Deploy to Vercel

### Option A — one-click from GitHub (recommended for a shareable link)

1. Create a new GitHub repo and push this folder:
   ```bash
   cd gruns-vercel
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/gruns-signal-desk.git
   git push -u origin main
   ```
2. Go to [vercel.com/new](https://vercel.com/new), import the repo, accept defaults, click **Deploy**.
3. You'll get a URL like `https://gruns-signal-desk.vercel.app` within 30 seconds.

### Option B — Vercel CLI (fastest, no GitHub needed)

```bash
npm i -g vercel
cd gruns-vercel
vercel
```

Follow the prompts. First deploy creates a preview URL; add `--prod` to ship to the production domain.

### Option C — drag and drop

Go to [vercel.com/new](https://vercel.com/new), drag the `gruns-vercel` folder into the drop zone, deploy.

---

## Local preview

```bash
npx serve . -p 3000
```

Then open `http://localhost:3000`.

---

## Structure

```
gruns-vercel/
├── index.html        # Signal Desk (main dashboard)
├── integrity.html    # Data Integrity & Robustness page
├── vercel.json       # Clean URLs + security headers
├── package.json      # For Vercel project detection
└── README.md
```

---

## Notes on the data

All numbers in this build are illustrative — designed to show what the product *would* surface with real data, and what the robustness case for those numbers would look like. The integrity page documents which data sources would feed the production version (Sprinklr, Brandwatch, Google Trends, Trustpilot/Amazon, Dynata longitudinal panel, first-party CDP, exit survey) and the specific tests that would run against each.
