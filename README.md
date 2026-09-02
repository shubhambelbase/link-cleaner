# Link Cleaner — Amazon, Daraz & UTM Remover

**One-click clean for Amazon `/dp/ASIN`, Daraz `/products`, AliExpress `/item`. Removes `utm_*`, `fbclid`, `gclid`, `spm`, `scm`, `wbraid` and 60+ trackers. Bulk clean + Scan Page. 100% local.**

![Local](https://img.shields.io/badge/100%25-local-C6FF00?style=flat) ![MIT](https://img.shields.io/badge/license-MIT-black)

## Install

1. **Chrome Web Store** — *[add your store link after publish]*
2. **Local dev:** `O:\link-cleaner` → Chrome → `chrome://extensions` → Developer mode → Load unpacked → select this folder
3. **Build zip for store:** `npm install` → `npm run build` → zip `dist/` (not the project root)

## Features

- **Right-click any link → Copy Clean Link** / **Copy as Markdown** `[title](url)`
- **Alt+Hover** popup on any link → tap Copy Clean (configurable: Off / Alt+Hover / On)
- **Ctrl+Shift+U** (⌘+Shift+U) → copy clean URL of current page
- **Scan Page** → collects up to 200 product links on the page → bulk clean
- **Bulk tab:** paste 1–200 URLs → Clean All → Copy / Copy as Markdown / Download .txt (de-duped)
- **Chips** show exactly what was stripped: `− utm_source  − fbclid  − spm`
- **History** (100, with removed chips) + **weekly counter** “37 removed this week”
- **QR** for the cleaned current URL (via `api.qrserver.com` only when you open it)
- **Settings (⚙):** hover mode, keep-list (e.g. keep `utm_campaign`)

### Marketplace-aware

| Site | Input | Output |
|---|---|---|
| Amazon | `/dp/B0XXXX?ref=...&tag=...&crid=...` | `/dp/B0XXXX` |
| Daraz | `/products/...html?spm=...&scm=...&pvid=...` | `/products/...html` |
| AliExpress | `/item/100500...html?spm=...` | `/item/100500...html` |
| YouTube | `youtu.be/ID?si=...`, `/shorts/ID`, `/embed/ID` | `youtube.com/watch?v=ID` |
| Short links | `t.co`, `bit.ly`, `tinyurl`, `lnkd.in`, `vm.tiktok` | HEAD-follow then clean |
| Generic | `?utm_* & fbclid & gclid & wbraid & spm/scm …` | stripped |

## Privacy

100% local. No analytics, no server. History in `chrome.storage.local` only. The only network is a `HEAD` to follow short-link redirects — nothing else leaves the browser. See `PRIVACY.md`.

## Project

```
src/
  lib/cleaner.js      # single source of truth — all cleaning logic
  background.js       # MV3 service worker: menus, history, stats, commands
  content.js          # standalone alt+hover popup (no imports)
  popup.jsx / popup.css / popup.html
  options.jsx / options.html
manifest.json         # MV3
vite.config.js        # builds popup + options + background + content to dist/src
scripts/copy-manifest.mjs
dist/                 # built output — zip this for the store
STORE_LISTING.md      # copy-paste store description + screenshots brief
PRIVACY.md            # privacy policy
OUTREACH.md           # posts to get first 1k users
```

## Build

```
npm install
npm run build   # vite build + copy manifest + icons to dist/
# then zip dist/ → upload to Chrome Web Store
```

## Roadmap

- [ ] Auto-clean on copy (clipboard watcher) — toggle already in Settings
- [ ] Landing page `linkcleaner.app` for SEO
- [ ] Firefox port (`manifest v2` compat)
- [ ] “Ask for review” nudge after 3 cleans
