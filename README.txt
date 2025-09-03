
Polska Quest — PWABuilder Ready Package
======================================

Contents
--------
- index.html (game, with manifest + service worker registration)
- manifest.webmanifest (PWA metadata, icons, colors, start_url)
- sw.js (offline caching of core files)
- icons/ (192 & 512 PNGs, maskable icon)
- README.txt (this file)

Quick Test Locally
------------------
1) In this folder run:
   python3 -m http.server 8080
2) Open: http://localhost:8080/
3) Use "Install App" in the browser (Chrome/Edge) to install as a PWA.
   (Service worker won't work over file://, so use the local server.)

Publish the PWA
---------------
Option A: GitHub Pages
  - Create a repo, upload these files at the repository root.
  - Settings → Pages → Deploy from main branch.
  - Your URL will look like: https://<user>.github.io/<repo>/

Option B: Netlify / Vercel
  - Drag & drop this folder to Netlify, or create a new Vercel project.
  - No build step required.

Build a Windows App with PWABuilder
-----------------------------------
1) Deploy your PWA (get a public HTTPS URL) — e.g. the Pages/Netlify URL.
2) Go to https://www.pwabuilder.com/windows
3) Paste your public URL and click "Start".
4) PWABuilder will analyze your manifest (already included) and generate
   a Windows package (MSIX) you can sideload or submit to the Store.
5) Download the package from PWABuilder. Follow their instructions to sign/side‑load.

Notes
-----
- Speech Recognition is browser/OS dependent; if not supported, users can Skip.
- You can change the app name, icons, and colors in manifest.webmanifest.
- If you later change files, bump the CACHE_NAME in sw.js to refresh offline cache.
