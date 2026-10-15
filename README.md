# hexopan-lab.github.io

The website of [Hexopan Lab](https://github.com/Hexopan-Lab), served by GitHub Pages at <https://hexopan-lab.github.io>.

It's a static page with no build step: edit `index.html` and push to `main`.

## Layout

```
index.html                  the page (styles inline)
site.webmanifest            app name, colours and icons
assets/brand/               source logo files
  hexopan-lab-icon.svg      rounded-tile mark, vector
  hexopan-lab-icon.png      rounded-tile mark, 1024px, transparent corners
  hexopan-lab-logo.jpg      full-bleed square mark, 1024px
assets/icons/               generated from assets/brand
  favicon.svg               browser tab (modern browsers)
  favicon.ico               browser tab fallback, 16/32/48px
  apple-touch-icon.png      iOS home screen, 180px, full-bleed
  icon-192.png, icon-512.png            manifest icons
  icon-maskable-512.png     Android adaptive icon, full-bleed
assets/og/og-image.png      link preview, 1200x630
```

## Regenerating icons

With ImageMagick, from the repo root:

```sh
T=assets/brand/hexopan-lab-icon.png F=assets/brand/hexopan-lab-logo.jpg
magick $T -define icon:auto-resize=48,32,16 assets/icons/favicon.ico
magick $F -resize 180x180 -strip assets/icons/apple-touch-icon.png
magick $T -resize 192x192 -strip assets/icons/icon-192.png
magick $T -resize 512x512 -strip assets/icons/icon-512.png
magick $F -resize 512x512 -strip assets/icons/icon-maskable-512.png
cp assets/brand/hexopan-lab-icon.svg assets/icons/favicon.svg
```

## Brand colours

| Navy | Cream | Red |
|------|-------|-----|
| `#232B6B` | `#F4EEDF` | `#C8473F` |
