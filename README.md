# PSX Portfolio Tracker

A simple, private portfolio tracker for **Pakistan Stock Exchange (PSX)** holdings.
It runs entirely in your phone or desktop browser — **no accounts, no servers, no API keys**.
Everything you enter is saved only in your own browser (using `localStorage`); nothing is ever sent anywhere.

## What it does

- **Home** — portfolio value (PKR + AUD), a **return breakdown** that keeps *unrealized P&L*, *realized P&L*, *dividends received*, and *total return* as separate, labelled measures, a **price-freshness summary** (fresh / stale / missing), sector allocation, and per-holding performance.
- **Holdings** — add, edit, and delete your own stocks. Each price is tagged **MANUAL — NOT LIVE** with the date you last updated it. A "✓ Still current" button re-stamps today's date without changing the number. Stale prices (older than your chosen number of trading days) are flagged.
- **Dividends** — log each payment individually (ticker, date, net amount received after tax) and see the running total and yield-on-cost-to-date.
- **Goal** — set a target (e.g. A$1,000,000 invested), see progress, and project the timeline at a chosen monthly contribution and return. Assumptions are stated on the tab.
- **Settings** — AUD→PKR rate (with the date you set it), cash balance, realized P&L, the stale-price threshold, your goal, backup/restore, and sample/clear.

### Important: this is NOT a live market tracker
There is **no live price feed**. PSX quotes cannot be fetched by a free static website, so **every price is one you type in yourself**. The app never claims a price is live, current, or sourced from PSX — it shows the last price you entered and when you entered it, and warns you when that may be out of date. Treat all figures as *based on your own inputs*.

The app ships with **sample data**. When you add your first real holding, the sample is cleared automatically.

## How to run it

**On your phone (recommended):**
1. Open the site URL in **Safari** (iPhone) or Chrome (Android).
2. Tap **Share → Add to Home Screen**.
3. It installs with an icon and opens full-screen, like an app.

**On a computer:** just open the URL, or open `index.html` directly in a browser.

**Hosting:** this is a static site. Any static host works — GitHub Pages, Netlify, Vercel, or Cloudflare Pages. There is no build step; the main page is `index.html` in the top folder.

### GitHub Pages (free)
Repo **Settings → Pages → Deploy from a branch → `main` / root folder → Save**. Your site appears at `https://<username>.github.io/<repo>/` after a minute.

### Vercel / Netlify (optional)
No build command and no output directory are needed — import the repo and deploy as a static site.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire app (HTML + CSS + JavaScript in one file). |
| `manifest.json` | Web app manifest — gives the home-screen app its name and icon. |
| `icon-180.png`, `icon-192.png`, `icon-512.png` | App icons. |
| `README.md` | This file. |

## PIN lock

The app opens behind a **4-digit PIN** every time (default `1994`). To change it, edit the line
`const PIN="1994";` near the bottom of `index.html`.

Note: this is a convenience lock to stop someone casually opening the app on your phone. It is **not**
strong security — the page runs in the browser, so a technical person could bypass it. Your real
protection is that **no actual holdings live in this code** — they stay only in your own browser.

## Backup & moving between phones

Open **Settings** in the app:
- **Export backup file** downloads your data as a `.json` file.
- **Import backup file** loads it back (e.g. on a new phone).
- **Copy / Paste sync code** moves your data via copy-paste between devices.

## Privacy & security

- No personal holdings are stored in this code — only sample data.
- No API keys, passwords, or tokens are used anywhere.
- All data you enter stays in your browser on your device.

## Disclaimer

This is a personal tracking tool for educational and informational use only. It is **not** financial, investment, or tax advice. Prices and figures are whatever you enter. Investing involves risk, including possible loss of capital.
