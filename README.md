# BEATVERSE
Static music discovery site. No server, no paid hosting. Music is streamed from **Internet Archive** (no key) and **Jamendo** (free client id), only tracks with Creative Commons or public-domain licences. Weather from **Open-Meteo** (no key).

## Run locally
Open `index.html` through any static server (e.g. `python3 -m http.server`), not by double-clicking, so browser APIs work.

## Jamendo setup (optional, recommended)
1. Create a free app at https://devportal.jamendo.com and copy the **client_id**.
2. Put it in `config.js` (it is a public id by design), **or** keep it out of the code: add a repository secret named `JAMENDO_CLIENT_ID` and use the Actions deploy below, which writes `config.js` at build time.

## Deploy on GitHub Pages
**With Git**
```
cd beatverse
git init -b main
git add .
git commit -m "BEATVERSE"
git remote add origin https://github.com/<you>/beatverse.git
git push -u origin main
```
Then on GitHub: Settings → Pages → Source: **GitHub Actions**. Optional: Settings → Secrets and variables → Actions → New secret `JAMENDO_CLIENT_ID`. The workflow in `.github/workflows/pages.yml` publishes at `https://<you>.github.io/beatverse/`.

**Without Git (browser only)**: create a repo on github.com → Add file → Upload files (drag everything, including the `.github` folder) → Settings → Pages → Source: Deploy from a branch → `main` / root.

## Notes
Language coverage depends on what creators have uploaded under open licences. Marathi, Haryanvi and Rajasthani are sparse; the app shows an empty state when nothing is found.
