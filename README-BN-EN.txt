# DUEL — Installable PWA package

This package turns the DUEL HTML app into an installable Progressive Web App (PWA).
It keeps the existing app code and its browser LocalStorage data key unchanged.

## Deploy with GitHub Pages (free)

1. Extract this ZIP on your computer or phone.
2. Sign in to GitHub and create a **new public repository** (for example: `duel-arena`).
3. Upload **the contents of this folder** to the repository's top level:
   - `index.html`
   - `manifest.json`
   - `service-worker.js`
   - `icons/` folder
   Do not upload the ZIP itself as the only file.
4. Open the repository's **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select branch **main** and folder **/(root)**, then Save.
7. Wait for GitHub Pages to publish the site. Your address will look like:
   `https://YOUR-USERNAME.github.io/duel-arena/`
8. Open that HTTPS address in **Google Chrome on Android**.
9. Open Chrome's ⋮ menu and choose **Install app** (or **Add to Home screen**, depending on Chrome version).

## Important notes

- Installation requires a secure HTTPS origin. GitHub Pages provides HTTPS.
- Open the published website at least once while online so the service worker can cache the app.
- After that first successful load, the app shell is available offline.
- Competition data remains in that browser/device's LocalStorage. It does not automatically sync between devices.
- Do not clear Chrome site data if you want to preserve locally stored competitions. Use DUEL's Export Backup option periodically.
- If you publish an update later, change `CACHE_NAME` in `service-worker.js` (for example, `duel-arena-pwa-v2`) so devices refresh the cached files.
- The optional in-app **Install DUEL** button appears only when Chrome signals that installation is available.
- On iPhone/iPad, open the site in Safari, tap Share, then **Add to Home Screen**.

## Troubleshooting

If Chrome does not show Install:
- Confirm the URL begins with `https://`.
- Confirm `manifest.json`, `service-worker.js`, and both icon files are reachable at the same site path.
- Open the site once online, reload it, and check Chrome's ⋮ menu again.
- Avoid opening `index.html` directly as a local file (`file://`); PWA installation does not work from a local file.

