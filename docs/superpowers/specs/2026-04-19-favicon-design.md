# Favicon Design: "IL" Rounded Square Badge

## Overview

Replace the current burger-icon favicon with an initials-based monogram that better represents the personal blog brand.

## Design

- **Shape:** 32×32 rounded square, `rx="5"`, fill `#343434`
- **Letterform:** "IL" centered, `#ffffff`, `font-family: system-ui, sans-serif`, `font-weight: 700`, ~15px
- **Letter spacing:** tight (`letter-spacing: -0.5px`) so both letters fit comfortably at small sizes
- **Format:** SVG — stays crisp on retina without a raster pipeline

## Delivery

- Replace `favicon.png` with the SVG (rename to `favicon.svg` or keep as `favicon.png` — SVGs served as `image/png` don't render correctly; use `favicon.svg`)
- Keep `favicon.ico` for older browser fallback
- Update `_includes/head.html` to add `<link rel="icon" type="image/svg+xml" href="/favicon.svg">` alongside the existing `.ico` fallback

## Files Changed

- `favicon.svg` — new file (replaces burger icon)
- `favicon.png` — can be removed or kept as PNG fallback
- `_includes/head.html` — add SVG icon link
