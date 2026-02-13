# Yu Bryan Zhou - Personal Website

Static personal website built from a minimal Bootstrap 4 template and deployed as a GitHub Pages site.

## Quick Start

```bash
npm install
npm run vendor
npm run dev
```

`npm run dev` starts BrowserSync and reloads when `*.html` or `css/*.css` changes.

## Repository Layout

- `index.html`: main website page.
- `old_news.html`: archived legacy page (not linked from `index.html`).
- `css/`: site styles and icon stylesheets.
- `img/`: site images.
- `files/`: downloadable files (for example resume PDF).
- `vendor/`: pinned runtime third-party assets used by the page.
- `docs/`: maintenance and optimization reference notes.

## Runtime Asset Policy

To keep the repo lean and predictable:

- Only commit third-party runtime files that are actually referenced by the site.
- Keep `vendor/` minimal (currently:
  - `vendor/bootstrap/css/bootstrap.min.css`
  - `vendor/bootstrap/js/bootstrap.bundle.min.js`
  - `vendor/jquery/jquery.min.js`)
- Do not commit `node_modules/`.

## Updating the Site

1. Edit content in `index.html`.
2. Update assets in `img/` or `files/` if needed.
3. If dependency versions change, run `npm run vendor` and commit only required `vendor/` files.
4. Verify locally with `npm run dev`.

## Maintenance Notes

See `docs/MAINTENANCE.md` for a practical checklist on safe cleanup and future optimization passes.
