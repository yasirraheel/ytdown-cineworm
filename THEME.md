# CineGrab Downloader theme: ONE LINE changes the whole site

Change ONLY this line in `public/build/css/styles.css`:

```css
:root{
  --brand:#2563eb;
  ...
}
```

`--brand-dark`, `--brand-soft` and `--brand-bg` are derived from `--brand` with
`color-mix`, so they follow automatically. Every green from the old VidSnap
template was replaced with `var(--brand)` / `var(--brand-dark)` /
`var(--brand-soft)` / `var(--brand-bg)`, and every green glow with
`color-mix(in srgb, var(--brand) N%, transparent)`. No other file needs a
colour edit, except the three things CSS cannot reach:

- `public/img/logo_small2.svg` (an SVG loaded as an image has no page CSS)
- `public/manifest.json` `theme_color`
- `<meta name="theme-color">` in the HTML pages

Current theme (2026-11-16): BLUE, --brand #2563eb.
Examples: yellow `--brand:#f5c518;`, green `--brand:#84bd07;`.
After changing --brand, bump `styles.css?v=` in the HTML pages so browsers fetch the new CSS.
