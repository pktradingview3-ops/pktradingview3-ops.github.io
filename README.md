# ROBINHOOD55 — Tools & Projects

**Live site:** https://pktradingview3-ops.github.io

A single-page catalog of open-source developer tools for Android automation,
wireless ADB, Wi-Fi file transfer and offline-first apps — built with shell,
Python and Kotlin on Kali Linux.

---

## What this is

The site is **one self-contained HTML file** (`index.html`) with no build step,
no framework and no dependencies. It fetches the repository list live from the
GitHub API, so the catalog always reflects what is actually published.

## Features

- **Live GitHub data** — repositories are pulled from the GitHub API at load
  time, with a 30-minute cache and a bundled fallback so the page is never
  empty.
- **Command palette** — `⌘K` / `Ctrl+K` / `/` to search tools and run actions
  (toggle theme, copy profile URL, filter by source). Arrow keys, Enter, Esc.
- **Filter, sort, view** — filter by All / On GitHub / Local; sort by Featured,
  Name, Stars or Recently updated; switch between grid and list.
- **Copy-to-clipboard** — install commands copy with one click, with a toast
  confirmation.
- **Dark and light theme** — persisted in `localStorage`.
- **Shareable URLs** — filter, sort, view and search state sync to the query
  string.
- **Accessible** — semantic markup, focus-visible states, ARIA labels,
  keyboard navigation, `prefers-reduced-motion` respected.
- **Responsive** — verified at 420 px mobile through 1440 px desktop.

## Run locally

```bash
git clone https://github.com/pktradingview3-ops/pktradingview3-ops.github.io.git
cd pktradingview3-ops.github.io
# just open it — no server needed
xdg-open index.html
```

To preview with the live GitHub fetch working (some browsers restrict `fetch`
on `file://`), serve it:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy

Any static host works. GitHub Pages is already configured for this repository:

```bash
git add -A
git commit -m "update"
git push
```

Pages redeploys automatically from the `main` branch root.

## Stack

Plain HTML, CSS and JavaScript. No framework, no bundler, no npm.

- Fonts: Inter Variable + JetBrains Mono Variable (via jsDelivr, with system
  fallbacks)
- Data: GitHub REST API (`/users/:user/repos`)

## License

MIT — see [LICENSE](LICENSE).
