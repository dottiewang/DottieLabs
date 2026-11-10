# dottielabs.com — static site

Plain HTML + CSS. No build step, no framework, no JavaScript (except the Print button on the QR sheet).

## Files
- `index.html` — homepage (header, hero, brand cards with QR codes, about, footer)
- `qr/index.html` — printable QR sheet (letter size, 2 × 3 grid). Private: not linked from the site, marked noindex. Visit dottielabs.com/qr directly.
- `styles.css` — all styles, including the print stylesheet
- `assets/dottie-labs-logo-lockup-transparent.png` — official lockup (used in header + QR sheet)
- `assets/dottie-labs-logo-lockup.png` — lockup on off-white (for social/OG use)
- `assets/dottie-labs-flame-mark.png` — flame only
- `assets/favicon-32.png`, `assets/favicon-192.png`, `assets/apple-touch-icon.png` — icons from the flame
- `assets/rings.svg` — top-right decorative rings
- `assets/qr/*.svg` — QR codes (error correction M, 4-module quiet zone, black on white)

## Open locally
Open `index.html` in a browser, or in VS Code use the Live Server extension. (The `/` logo link and `qr/` folder link work best when served, not opened as a file.)

## Deploy
Upload the folder as-is to any static host: Netlify (drag and drop), Cloudflare Pages, Vercel, GitHub Pages, or S3. Point dottielabs.com at it. `/qr/` resolves to `qr/index.html` automatically.

## Print the QR sheet
Go to `/qr/`, click **Print (letter)** (or Cmd/Ctrl+P). Choose Letter, scale 100%, margins Default, and turn on "Background graphics" for best results. Each code prints at ~2.1 in.

## Editing brands
Each brand is one `<li>` in `index.html` and one in `qr/index.html`. If a URL changes, regenerate its QR (any generator that outputs SVG: error correction M or higher, no center logo) and replace the file in `assets/qr/`.
