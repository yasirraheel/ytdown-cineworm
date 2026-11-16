# ClipDown theme

The whole site takes its brand colour from ONE line in `public/build/css/styles.css`,
at the very top of the file:

```css
:root{
  --brand:#84bd07;
  --brand-dark:#6da305;
  --brand-soft:#f6fbf0;
  --brand-bg:#f7fcef;
}
```

To change the colour of the entire site, change only the `--brand` line.
Everything else (buttons, links, hero highlights, hover rings, pills and
step cards) uses `var(--brand)`, `var(--brand-dark)`, `var(--brand-soft)`
or `var(--brand-bg)`, so it follows automatically. Do not search and
replace colours across the files.

Examples (change the one line, nothing else):

- Yellow: `--brand:#f5c518;`
- Blue: `--brand:#2563eb;`

If you change `--brand` a lot, you may also want to adjust `--brand-dark`
(used for hover text and small headings) and `--brand-soft` / `--brand-bg`
(used for pale card and hero backgrounds) to matching tones, but the
site still works if you only change `--brand`.

Two places keep the default green as a literal value and are NOT driven
by the variable: the `<meta name="theme-color">` tag in each HTML page
(a meta tag cannot use `var()`), the `theme_color` in `public/manifest.json`,
and the text logo `public/img/logo_small2.svg` (an SVG loaded as an image
has no page CSS context). Change those three by hand if you recolour.
