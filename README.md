# C³ — Complementary Colors Creator

**Live:** [c3lab.vercel.app](https://c3lab.vercel.app)

A small, focused palette tool for designers. Give it a colour — as a HEX code, from a picker, or from a photo — and it builds an eight-colour palette you can copy straight into Figma or code.

By nuforms lab.

---

## What it does

**Three ways in**

- **Upload** — drop a photo; C³ pulls up to eight of its real colours, exactly as they appear in the image.
- **Code** — type or paste a HEX value.
- **Picker** — pick a colour by eye.

**Four harmonies**

| Harmony | Rule | Feel |
|---|---|---|
| Complementary | base + its opposite on the colour wheel (180°) | strongest contrast, two poles |
| Triadic | three points spaced evenly (120°) | bright, balanced |
| Tetradic | four points in a square (90°) | richest, four colours |
| Mono | one hue, only lightness and chroma change | calm, tone-on-tone |

**Photo mode.** After an upload, a **Photo** tab shows the colours exactly as they are in the image. The harmonies then adapt to the photo: partner colours are muted to the photo's level of colour, their lightness follows the photo, and real colours from the image are used whenever one sits close to the generated one.

**Colour weight.** Below the palette, floating circles show how much of the photo each colour covers.

**Export.** *Copy SVG* (paste straight onto a Figma canvas — every capsule becomes a named layer), *Copy CSS* (custom properties), *Copy JSON*.

**Small things.** Click a colour to copy its HEX. Double-click a colour to make it the new base. Light and dark themes. Names for every colour, plus the Pantone name when a colour is a close match to a Pantone Colour of the Year.

## How the palettes are built

Harmonies are calculated on the **OKLCH** colour wheel rather than HSL. In OKLCH, equal lightness *looks* equally light, so a partner colour sits at the same visual weight as the base instead of glowing (yellows) or sinking (blues). Colours that fall outside what a screen can show are brought back by lowering their chroma while keeping hue and lightness.

Photo colours are real pixel colours: the image is sampled without blending, similar colours are grouped, and each group is represented by its most common exact colour. Nothing is averaged, so flat brand colours come back exactly and no muddy in-between colours are invented.

## Project

The whole app is one file — `index.html` — with no build step and no dependencies apart from two Google Fonts (Syne, Space Mono).

```
index.html   the app: markup, styles and script
README.md    this file
```

Run it locally by opening `index.html` in a browser.

## Deploy

Hosted on Vercel. Every push to `main` deploys automatically to [c3lab.vercel.app](https://c3lab.vercel.app).

## History

- **v2** — C³ landing: layered capsule palette, photo colour weights, OKLCH engine with four harmonies.
- **v1** — the original Complimentary Color Creator; still in the git history (commit `1ffb2a4`).
