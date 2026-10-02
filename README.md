# AuréMED website

Responsive static website for AuréMED treatment coordination in Cairo.

## Included

- Six languages: Saudi Arabic (RTL), English, German, Italian, Spanish and Russian.
- Interactive treatment exploration and five-stage journey.
- Silent six-second hero video with a pause control and reduced-motion handling.
- Dedicated `/booking/` page for an introductory Zoom meeting request.
- Coordinator preference (Nicolas, Khaled or no preference), meeting language, treatment, proposed date/time/time zone and contact details.

## Publishing on Cloudflare Pages

1. Put this README and the `dist` folder in a GitHub repository owned by you. A private repository is suitable.
2. In Cloudflare, open Workers & Pages, create a Pages application and import that repository.
3. Use the production branch containing these files (normally `main`), framework preset `None`, build command `exit 0`, and build output directory `dist`.
4. Deploy. Cloudflare supplies a `pages.dev` address.
5. Add a domain you own through the project's Custom domains settings and follow the DNS instructions.

No package installation or framework compilation is required.

Official instructions: https://developers.cloudflare.com/pages/framework-guides/deploy-anything/
Custom domains: https://developers.cloudflare.com/pages/configuration/custom-domains/

## Current booking behaviour

The form prepares a request addressed to info@auremed.com. The visitor reviews and sends it in their email app, or copies the text. It does not submit to a database, check real calendar availability, create a Zoom meeting or send an automatic confirmation. The AuréMED team confirms availability and supplies the Zoom link manually. Connecting a scheduling service can replace this handoff later.

No medical-record upload or online payment capability is included. Only the website language preference is stored in browser local storage. Form values remain in page memory until navigation or refresh.

## Editing

- `dist/locales.js`: all six language dictionaries.
- `dist/app.js`: interactions and page rendering.
- `dist/style.css`: responsive styles and RTL layouts.
- `dist/index.html` and `dist/booking/index.html`: page entry points.
- `dist/hero-motion.mp4`, `dist/hero-poster.jpg`, `dist/hero.png`: visual assets.

Hero imagery is illustrative. It is not clinical evidence or a patient result.

## Local preview

From this folder, run `python3 -m http.server 8080 --directory dist` and open http://localhost:8080. Open `/booking/` for the meeting request page. Opening HTML files directly with `file://` will not resolve root-relative assets correctly.
