# DAYFLOW PWA

Installable offline-first Progressive Web App for Android and Linux desktop browsers.

## Included
- Daily checklist and custom activities
- Date-specific history and recent-day summaries
- Offline app shell after the first successful online load
- Focus timer with 15, 25 and 40 minute presets; pause, resume and reset
- Daily reminder settings and browser notifications when supported
- JSON export/import backup

## Install on Android via GitHub Pages
A PWA requires HTTPS (or localhost for development). Opening `index.html` directly in the Files app does not enable installability or offline caching.

1. Extract this ZIP on your Linux Mint computer.
2. Create a GitHub repository, for example `dayflow-pwa`.
3. Upload the contents of this project to the repository root: `index.html`, `styles.css`, `app.js`, `sw.js`, `manifest.webmanifest`, `.nojekyll`, `icons/`, and `README.md`.
4. Open the repository's **Settings → Pages**.
5. Under Build and deployment, select **Deploy from a branch**, choose `main` and `/(root)`, then Save.
6. Wait for GitHub Pages to publish the HTTPS URL, usually `https://YOUR-USERNAME.github.io/dayflow-pwa/`.
7. Open that URL in Chrome on Android while online, wait for the page to finish loading.
8. Chrome menu (⋮) → **Install app** or **Add to Home screen** → confirm.
9. Launch DAYFLOW from its new Home screen icon. After first load, try enabling airplane mode to check offline access.

## Test on Linux Mint
From the extracted project folder, run `python3 -m http.server 8000`, then visit `http://localhost:8000` in a browser. Service workers work on localhost. This is a PC test address, not directly accessible from your phone.

## Data and limitations
Data is saved in browser localStorage on each device and is not synced automatically. Use Export data and Import data to move a JSON backup between devices. Clearing browser site data may erase history.

Reminders are best-effort: the app checks the reminder time while open or when it becomes active. Browsers can suspend background tasks, so this PWA cannot guarantee notifications at an exact time while fully closed. Use a native app for reliable alarm-style reminders.

The focus timer is intended to run while the page is active; browser or OS suspension may affect it. This project has not been certified or tested on every Android/browser version.
