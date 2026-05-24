# Kaffy — Landing Page (Lite / Light theme)

Client-presentable prototype of the Kaffy landing page (light "lite-v-1"
theme), exported from Claude Design. It's a single self-contained `index.html`
plus its image assets — no build step, no dependencies to install.

> The dark v2 theme lives on the `claude/tender-maxwell-Hnfwr` branch.

## Preview locally

Open `index.html` directly in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy

Any static host works — the entry point is `index.html` at the repo root:

- **GitHub Pages** — Settings → Pages → deploy from this branch, root folder.
- **Netlify / Vercel** — import the repo; no build command, publish directory `/`.
- **Cloudflare Pages** — connect repo; framework preset "None".

## Notes

- Fonts (Space Grotesk, Manrope, JetBrains Mono) load from Google Fonts, so a
  network connection is needed for the intended typography.
- All other assets (images, hero video) are bundled under `images/`.
- The page is responsive (320px phones → desktop) with a mobile drawer menu and
  sticky shop CTA, and includes scroll-reveal animations, count-up stats, and a
  looping hero video.
