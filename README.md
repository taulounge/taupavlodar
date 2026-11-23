# TAU Lounge Restaurant — online ordering frontend

Responsive React + Vite project with 7 routes, RU/KZ language toggle, localStorage cart, menu search/categories and WhatsApp order handoff.

## Run locally
1. Install Node.js 20+.
2. `npm install`
3. `npm run dev`
4. Production bundle: `npm run build`

## Source-data notes — review before public launch
- Menu names/prices/descriptions are transcribed from the text layer of the supplied 44-page PDF. The PDF contains many image-only pages; the text extraction is incomplete. Some entries are marked with an unknown price and should be verified against the visual menu / restaurant.
- The current menu card photos are intentionally neutral placeholders, not fake photos of dishes. Add approved original dish photos to `public/assets` and wire them to menu records.
- Restaurant address and delivery zone/fees are not confirmed in the extracted text and are therefore not invented.
- Kazakh UI labels are included; dish-name translations are currently English fallback / Russian for several menu items and need native Kazakh proofreading before launch.
- WhatsApp checkout opens a prefilled message to +7 700 424 2607. It does not transmit an order to a server, charge payment, or verify delivery availability. The guest must press Send in WhatsApp.
- The 10% service fee is disclosed; it is not silently added to the WhatsApp total because the PDF states it is added to the order cost but does not specify whether delivery orders use the same rule. Confirm whether the 10% applies to online delivery before enabling calculation.

## Brand assets
- `public/assets/tau-logo.jpg` is the user-provided logo and is used as the favicon and header mark.


## GitHub Pages deployment
1. Push the complete project folder contents to the `main` or `master` branch (keep `.github/workflows/deploy.yml`).
2. In GitHub: Settings → Pages → Build and deployment → Source: **GitHub Actions**.
3. Open the repository Actions tab and wait for **Deploy TAU Lounge to GitHub Pages** to finish successfully.
4. Open the Pages URL shown in the deployment job. Routes use hash URLs (for example `/#/menu`) so refreshes work on GitHub Pages.

Do not publish the raw `src` folder as a static site. GitHub Actions builds the React/Vite app into `dist` before publishing it.
