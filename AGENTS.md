# AGENTS.md

## Cursor Cloud specific instructions

### Overview
This repository is a single, self-contained static web app: **"Codi · 나의 옷장"** (a Korean wardrobe / outfit-recommendation SPA). The entire product is one file, `index.html`, with inline CSS and vanilla JS. There is **no backend, no build step, no package manager, and no dependencies** committed to this repo (the `.gitignore` intentionally excludes an external Python backend that is not part of this checkout).

### Running the app (dev)
Serve the single static file with any static server from the repo root, then open `index.html`:

```
python3 -m http.server 8000
# open http://localhost:8000/index.html
```

`node` is also available (`npx serve .`) if preferred. The file can even be opened directly via `file://`, but serving over HTTP is cleaner.

### Data & persistence
- All user data (closet items, worn history) persists in the browser's `localStorage` — there is no database. Clearing site data resets the app to its seed items.
- The weather widget calls the public **Open-Meteo** API (`api.open-meteo.com`, no key required, Seoul coordinates hard-coded). It is **optional**: core closet/recommendation features work without network access; the weather badge just degrades gracefully.

### Lint / test / build
- There is **no lint, test, or build tooling** in this repo. "Testing" means opening the app in a browser and exercising the UI (e.g. add a closet item, view outfit recommendations).

### Notes
- There are no environment variables or secrets required.
