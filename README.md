# TravelFX — Currency Converter for Travelers

A clean, mobile-first currency converter built for iPhone. Live exchange rates,
pinned currencies, VAT / tax / discount math, and offline support after first load.
All your data stays on your phone.

## Features

- **Live USD ↔ foreign currency** with rates from `open.er-api.com` (no API key, no signup)
- **Pin any currencies** for one-tap conversion at a glance
- **USD → Foreign**: optional 7.5% U.S. sales tax (configurable), VAT %, discount %
- **Foreign → USD**: instant USD value, plus the price *with* U.S. sales tax for fair comparison
- **Phone-to-phone transfer**: export/import a JSON backup of all your settings
- **Excel export (.xlsx)**: full rate table + your pinned currencies + settings
- **Works offline** after first visit (PWA / service worker)
- **Dark mode** automatic
- **Local-only data** — nothing is sent anywhere except the rate API

## Run on your iPhone (GitHub Pages)

1. Create a new public repo on GitHub, e.g. `travelfx`.
2. Upload everything in this folder to the repo root.
3. **Settings → Pages → Source: `main` / root** → Save.
4. Wait ~1 minute for the green check, then visit
   `https://YOUR-USERNAME.github.io/travelfx/` in **Safari** on your iPhone.
5. Tap **Share → Add to Home Screen**. The app launches full-screen with its own icon.

## Phone transfer

On the old phone:
- Settings → **Export** → save the JSON to Files / iCloud / AirDrop.

On the new phone:
- Open the app → Settings → **Import** → pick the JSON file.

Your pinned currencies, defaults, and last-known rates come across.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app (HTML + CSS + JS in one file) |
| `manifest.json` | PWA manifest (name, icons, colors) |
| `service-worker.js` | Offline cache |
| `icon.svg` | Vector icon (plane + dollar) |
| `icon-192.png` / `icon-512.png` | PWA icons |
| `apple-touch-icon.png` | 180×180 iOS home-screen icon |
| `favicon-32.png` | Tab favicon |

## Privacy

No analytics. No accounts. Rate requests go directly from your browser to
`open.er-api.com`. Settings live in `localStorage` on this device only.

## Tech notes

- Single-file vanilla HTML/CSS/JS — no build step.
- Uses `SheetJS` (loaded from cdnjs) for Excel export.
- Rate provider: `https://open.er-api.com/v6/latest/USD` (free, public).
- iOS-friendly: safe-area insets, 44px+ tap targets, no zoom on focus, full PWA.
