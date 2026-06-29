# Patch Sheet

DMX patch viewer for [Blackout](https://blackout-app.com) lighting console exports.

Built for film and commercial production sets — riggers receive a CSV patch list and open it directly on their phone without any installation.

**Live:** [patch.wallinfilmljus.se](https://patch.wallinfilmljus.se)

---

## Features

- Reads CSV exported from Blackout → Patch → Export
- Groups fixtures by universe, sorted by DMX address
- Shows fixture number, DMX address, mode, label, fixture type, description, footprint
- Color-coded left border from `LABEL_COLOR`
- Tap any fixture to mark it as done (dimmed)
- Progress bar tracking patched fixtures
- Search across all fields
- Light / dark mode
- Swedish / English
- PWA — add to home screen for app-like experience
- Auto-reads clipboard on load (used with iOS Shortcut)
- Service Worker for offline use and update notifications

---

## iOS Shortcut

Installs a shortcut that copies the CSV to clipboard and opens the app — one tap from the Share Sheet.

**[Install shortcut](https://www.icloud.com/shortcuts/36e0f80c57e24df898a5b9b7bfb215be)**

Flow:
1. Receive CSV via AirDrop or iMessage
2. Press and hold the file → Share
3. Choose **Patch Sheet**
4. App opens and reads the patch automatically

---

## Files

| File | Description |
|------|-------------|
| `index.html` | Single-file app — all HTML, CSS, JS |
| `sw.js` | Service Worker — caching and update notifications |
| `manifest.json` | PWA manifest |
| `icon-*.png` | App icons for iOS and Android |
| `CNAME` | Custom domain configuration |

---

## Updating

1. Edit `index.html`
2. Bump `VERSION` in `sw.js` (e.g. `v9` → `v10`)
3. Commit and push — users with the app installed will see an update banner

---

## CSV Format

Expects Blackout's standard export format:

```
FIXTURE_NUMBER,ADDRESS,ADDRESS_FOR_LABELS,MANUFACTURER,FIXTURE_TYPE,DMX_FOOTPRINT,DESCRIPTION,MODE,LABEL,LABEL_COLOR
501,1-20,1/001,ARRI,SkyPanel S30-C,20,CCT + RGBW 16bit,Mode 6,S30-C 1,#5aaa8b
```

---

*Wallin Film Ljus AB*
