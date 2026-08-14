# Duel and Battle — website source

This is a plain HTML/CSS/JS rebuild of the `duelandbattle.com` landing page,
reconstructed from the live Canva-hosted site and Canva design so it can be
opened and edited with Claude Code (or any code editor) going forward.

## Why a rebuild instead of an "export"

Canva Sites don't offer a code export — the live page is served from Canva's
own rendering engine inside a locked-down iframe, so there's no HTML/CSS file
to download directly. This project is a from-scratch reconstruction that
matches the original's layout, copy, and color palette as closely as
possible, written as clean, ordinary web files you can hand to Claude Code.

## What's here

```
index.html        All page sections (hero, about, how to buy, shipping, contact, footer)
css/styles.css     All styling — colors, type, and layout live in CSS custom
                    properties at the top of the file for easy tweaking
js/script.js       Mobile nav toggle
assets/logo.svg    Hand-recreated shield/sword/lightning emblem (vector, matches the original)
```

No build step, no dependencies — just open `index.html` in a browser, or serve
the folder with any static server.

## Things worth double-checking / finishing

- **TCGPlayer links**: I couldn't read the real storefront/category URLs out
  of the live site (they're inside a cross-origin iframe I can't inspect), so
  every "Shop on TCGPlayer" / category link currently points to
  `https://www.tcgplayer.com/` as a placeholder. Swap in your actual
  storefront and per-game filter URLs.
- **Fonts/colors**: matched by eye from screenshots of the live site (a
  small-caps serif for headings — currently Playfair Display — and a sans for
  body/nav text — currently Inter — on a near-black background with a muted
  gold accent). Close, but not guaranteed pixel-identical to the Canva
  original. All of it is controlled from the `:root` variables at the top of
  `css/styles.css`.
- **Logo**: recreated as an SVG (`assets/logo.svg`) rather than pulled as a
  raster file, so it's crisp at any size and easy to recolor. If you'd rather
  use your original Canva-exported logo file, just drop it in `assets/` and
  update the `<img src>` references in `index.html`.

## Using this with Claude Code

1. Unzip the project folder somewhere on your machine.
2. Open a terminal in that folder and run `claude` (or open the folder in
   your editor with the Claude Code extension).
3. Ask for changes in plain language, e.g. "make the gold a bit warmer," "add
   a FAQ section above the footer," "swap the hero button copy." Claude Code
   can edit these files directly.
4. When you're ready to publish, this static site can be deployed anywhere
   that serves plain HTML (Netlify, Vercel, GitHub Pages, S3, your existing
   host, etc.) and pointed at your `duelandbattle.com` domain.
