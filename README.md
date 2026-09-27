# Household Budget Planner (Desktop)

The **Household Budget & Car Payoff Planner** packaged as a Windows desktop app
with Electron: monthly budget planning, car payoff math, and a ZIP-code
property-tax estimator, all offline in one window.

## Run it (development)

```sh
npm install
npm start
```

## Build the Windows installer locally

```sh
npm install
npx electron-builder --win nsis portable
```

The `.exe` installer and portable build land in `dist/`.

## Automatic builds

Every push to `main` auto-builds the installer and portable app via GitHub
Actions — check the **Actions** tab on the repo for the `windows-installer`
artifact from the latest run.

## Updating the app

The app itself is a single HTML file. To update it, copy the newest planner HTML
over `app/index.html`, commit, and push — the Actions workflow builds a fresh
installer for you.

> Note: the ZIP-code property-tax estimator needs internet access (it looks up
> the ZIP at `https://api.zippopotam.us`). Everything else works fully offline.
