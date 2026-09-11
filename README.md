# Link Cleaner — Bulk UTM & Affiliate Cleaner

One click, zero tracking. Strip `utm_*`, `fbclid`, `gclid`, `spm/scm`, affiliate tags & tracking wrappers — one link or 200 at once. 100% local, no account.

## Brand Ad

<video src="assets/brand-ad.mp4" controls width="100%" poster="icons/icon128.png">
  Watch the brand ad: <a href="assets/brand-ad.mp4">assets/brand-ad.mp4</a>
</video>

## What it does

* **Clean tab** — clean current page URL, see exactly what was removed (`−utm_source` chips), Copy / Rich link / QR code
* **Bulk (up to 200)** — paste URLs → Clean All → Copy / Markdown / Download `.txt` / `.csv` (`Original URL,Clean URL,Domain,Trackers Removed`)
* **Scan Page** — collects up to 200 links on the page, shows found / tracked / clean breakdown, one-click transfer to Bulk
* **Marketplace-aware** — Amazon → `/dp/ASIN`, Daraz → `/products/...html`, Shopee / Temu / YouTube (`youtu.be`, `shorts/`, `embed/` → `watch?v=`) / TikTok / Instagram / X / Reddit / Pinterest path-only
* **Short links** — unwraps `t.co`, `bit.ly`, `tinyurl`, `lnkd.in`, `amzn.to` (HEAD follow, only on explicit request)
* **History + stats** — last 100 cleans stored locally, click to re-copy, weekly counter
* **Shortcuts** — Right-click → Copy Clean Link / Copy as Markdown, `Alt+Hover` in-page badge, `Ctrl+Shift+U` clean current page
* **Themes** — Light / Dark / Auto

## Install / Dev

```bash
npm install
npm run dev      # Vite dev server
npm run build    # production build -> dist/ (+ manifest/icons copy)
node test-cleaner.mjs       # 118 unit tests
node test-content-sync.mjs  # 21 parity tests (cleaner.js <-> content.js)
```

Load `dist/` via `chrome://extensions` → Developer mode → Load unpacked. See `STORE_LISTING.md` for Web Store copy.

## Privacy

The extension is 100% client-side — no analytics, no server. Details: [Privacy Policy](https://shubhambelbase.github.io/link-cleaner/privacy.html).

Note: that hosted policy page itself uses Google Analytics (`gtag.js`, `G-Y34X8ZVVBR`) for page-view counts. The extension sends nothing.

Contact: [shubham982615@gmail.com](mailto:shubham982615@gmail.com) · Source: [github.com/shubhambelbase/link-cleaner](https://github.com/shubhambelbase/link-cleaner)
