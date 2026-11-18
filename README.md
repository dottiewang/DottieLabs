# dottielabs.com — static site

Plain HTML + CSS. No build step, no framework. The only JavaScript is the Print button on the QR sheet.

## Files
- `index.html` — homepage (header, hero, project cards with QR codes + URL labels, about, footer)
- `qr/index.html` — printable QR sheet (letter size, two-column grid across pages). Private: not linked from the site, marked noindex. Visit dottielabs.com/qr directly.
- `styles.css` — all styles, including the print stylesheet
- `assets/dottie-labs-logo-lockup-transparent.png` — official lockup (used in header + QR sheet)
- `assets/dottie-labs-logo-lockup.png` — lockup on off-white (for social/OG use)
- `assets/dottie-labs-flame-mark.png` — flame only
- `assets/favicon-32.png`, `assets/favicon-192.png`, `assets/apple-touch-icon.png` — icons from the flame
- `assets/rings.svg` — top-right decorative rings
- `assets/qr/*.svg` — QR codes (error correction M, 4-module quiet zone, dark on white or transparent)

## Open locally
Open `index.html` in a browser, or in VS Code use the Live Server extension. (The `/` logo link and `qr/` folder link work best when served, not opened as a file.)

## Deploy (GitHub Pages)
1. Put the **contents** of this folder at the root of the repo (so `index.html` and `CNAME` sit at the top level).
2. Repo → Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.
3. Custom domain: `dottielabs.com` (already set by the `CNAME` file). Tick **Enforce HTTPS** once it's available.
4. At your domain registrar, add DNS records:
   - `A` records for `@`: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - `CNAME` for `www` → `<your-github-username>.github.io`
5. Push to `main`. The site redeploys automatically in about a minute.

`/qr/` resolves to `qr/index.html` automatically. Unknown URLs show `404.html`.

## Standard site files
- `CNAME` — tells GitHub Pages the custom domain. Don't delete it.
- `.nojekyll` — tells GitHub to serve files as-is, without its Jekyll build step.
- `404.html` — the "page not found" page.
- `robots.txt` — lets search engines index the site, excludes `/qr/`, and points to the sitemap.
- `sitemap.xml` — the page list for Google. Update `lastmod` when content changes.
- `site.webmanifest` — app name, colors and icon for phones and "Add to Home Screen".
- `assets/og-image.png` — 1200 × 630 preview image shown when the link is shared (iMessage, Slack, LinkedIn, X).
- In `index.html`: canonical URL, Open Graph and Twitter tags for link previews, and schema.org Organization data for Google.

## Print the QR sheet
Go to `/qr/`, click **Print (letter)** (or Cmd/Ctrl+P). Choose Letter, scale 100%, margins Default, and turn on "Background graphics" for best results. Each code prints at ~2.1 in.

## Editing projects
Each project is one `<li>` in `index.html` and one in `qr/index.html`. If a URL changes, regenerate its QR (any generator that outputs SVG: error correction M or higher, no center logo) and replace the file in `assets/qr/`.

