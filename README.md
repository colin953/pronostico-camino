# Pronóstico Camino de Acceso

Installable web app (PWA) for the Baguales access road avalanche forecast, in Spanish and English with a language button.

## Where the data comes from

The app reads two tabs of the "Pronostico Camino de Acceso" Google Sheet, which are published to the web as CSV:

- `Pronostico Espanol` (gid 1724057832)
- `English Forecast` (gid 1450128190)

It reads fixed cells from those tabs (date D7, level B10, comments B14, and so on), so the sheet's formulas still do the work: expiry check, translations, observation lookups. If the layout of those tabs changes, update `readTab()` in `index.html`.

Published sheets can lag a few minutes behind a new form response.

## Behaviour

- Refreshes every 5 minutes and whenever the app is reopened.
- Remembers the language chosen on each device. `?lang=en` opens in English.
- Keeps the last forecast downloaded and shows it offline, marked as offline.

## Files

- `index.html`: the app
- `manifest.webmanifest`, `sw.js`, `icons/`: make it installable and work offline

## Install on a phone

Open the GitHub Pages address, then:
- **Android (Chrome):** menu › *Add to Home screen* / *Install app*
- **iPhone (Safari):** Share › *Add to Home Screen*
