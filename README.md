# Kaffy — Landing Page (lite-v-2)

Client-presentable prototype of the Kaffy landing page (lite-v-2 — light
theme with built-in dark mode toggle), exported from Claude Design. It's a
single self-contained `index.html` plus its image assets — no build step, no
dependencies to install.

> The original dark v2 theme lives on the `claude/tender-maxwell-Hnfwr` branch.

## What's in v2 (vs. lite-v-1)

- **Light / dark theme toggle** in the nav (sun/moon). Choice persists in
  `localStorage`; first-time visitors get their system preference. No flash.
- **Single Amazon offer** replaces the three pricing tiers — one product card
  with a "Buy on Amazon" CTA wired from a single source of truth.
- **Top bars frozen** — review ticker and announcement bar are no longer
  animated marquees.
- **Corrected dosing** — Cognizin 30 mg, L-Theanine 75 mg (ingredient cards
  + FAQ).
- **15 pouches per puck** throughout (was 20).

## Before deploy: set the Amazon link

Open `index.html` and replace the `AMAZON_URL` constant near the bottom of
the main `<script>` block with the real Kaffy listing URL — every "Buy on
Amazon" CTA reads from it.

```js
const AMAZON_URL = "https://www.amazon.com/"; // ← replace with the Kaffy listing
```

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
