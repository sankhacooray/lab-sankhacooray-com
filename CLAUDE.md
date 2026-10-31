# lab.sankhacooray.com — project memory

Single-file hub (`index.html`, CSS inline) on GitHub Pages; deploy = `git push` to `main`.
Card thumbnails live in `thumbs/` as WebP at 400/600/800 px (`<name>-400.webp`, `<name>-600.webp`,
`<name>.webp`) served via `srcset`; the original 800×420 JPGs are kept as sources.

## Lighthouse

<!-- lighthouse-optimized: 2026-10-31 -->
- Baseline mobile (31 Oct 2026): performance 79 · accessibility 94 · best-practices 100 · SEO 100.
- Fixed: Google Fonts non-blocking (preconnect + `media=print` swap + noscript, dropped unused weights/italic);
  thumbs → WebP with `srcset`/`sizes` + width/height; first thumb (mobile LCP) eager with `fetchpriority=high`;
  `--text-muted` raised to ≥4.5:1 on `--surface2` in both themes (light #5f6a7b, dark #7d89a2) and the
  "in the lab" dimming moved off the chip; card titles h3 → h2 (heading order).
- Left: cache TTL on thumbs (GitHub Pages can't set headers); shared footer/analytics/gtag findings are handled centrally.
