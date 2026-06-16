# CLAUDE.md — working notes for Meg's Café

Context for an AI assistant picking up this repo mid-stream. The human-facing
overview is in [`README.md`](README.md).

## What this is

A one-file static website for **Meg's Café**, a home-based café in Gilbert, AZ.
No framework, no build, no package manager — everything lives in `index.html`
(inline `<style>` and `<script>`). Fonts load from Google Fonts (Hanken
Grotesk). Open the file in a browser to preview; there is nothing to compile.

## Design system (the "Hunnybee" minimal look)

CSS custom properties at the top of `index.html`:

- `--bg:#f5f7ef` warm cream · `--green:#3d6b4c` headings/brand ·
  `--green-deep:#2f5640` · `--gold:#8a6418` eyebrows/accents · `--ink:#26271f`
  body text · `--muted:#56564d`
- Font: **Hanken Grotesk** (one family, several weights). Headings are uppercase,
  bold (800), letter-spaced. Section "eyebrows" are gold, bold, uppercase.
- Layout is a single centered column (`.wrap`, max-width 820px) with generous
  whitespace. **Keep it simple** — the owner explicitly rejected busier designs.
  `index.riso.html` is the previous, ornate version kept as a "what not to do."

## Conventions

- Single file. Edit `index.html` directly and match the existing
  CSS-variable / class style.
- Brand name is **Meg's Café** — curly apostrophe (`’`) and accented **é**. Keep
  this consistent in body copy, the hero wordmark, and the footer.
- Nav is anchor-based (`#home #menu #order #about`) with a small JS scroll-spy
  that toggles `.active` on the current section's link.

## Must-keep features (owner's explicit requirements)

1. **Scheduling** — order-ahead with a chosen pickup time. The Order section's
   three-step flow ("Build it → Pick a time → Pay & go") leads to **Hotplate**,
   which provides scheduling + ordering + payment for home/cottage food
   businesses.
2. **Order options** — the "Make it yours" chip builder on the Menu
   (temperature / milk / flavor / espresso). It's informational plus a small JS
   summary line; the actual transaction happens on Hotplate.

Do not remove either of these when editing.

## Open TODOs

- **Hotplate URL** — the "Order on Hotplate" button links to
  `https://www.hotplate.com/` (placeholder, marked with a `TODO` comment in
  `index.html`). Swap in the real shop link once it exists.
- **Handles** — `@cottagecafe` / `hello@cottagecafe.com` are legacy and don't
  match "Meg's Café." Update when the new handles are known.
- **Accent** — site uses "Café"; confirm against plain "Cafe" with the owner.

## Re-lettering the poster (`latteart.jpg`)

The hero poster has the café name baked into the pixels. To change it:

1. Start from `latteart.original.jpg` (820×1024, pure-white background).
2. Paint a white rectangle over the centre text block — roughly
   `x 236–586, y 384–586`.
3. Draw the new name centred near `(411, 486)` in **Fraunces** (variable font —
   download from Google Fonts), deep green `(33, 74, 49)`, as two centred lines.
4. Save over `latteart.jpg` at JPEG quality ~93.

This was done with Python + Pillow, using
`ImageFont.set_variation_by_axes(...)` to set Fraunces' opsz / weight / SOFT /
WONK axes (opsz max, weight ~600, SOFT max, WONK 1). The font was kept in
`.fonts/` (gitignored) — refetch from Google Fonts as needed.

## Deploy

Static — host anywhere. Easiest is GitHub Pages (Settings → Pages → `main` /
root), which publishes to `https://vancouvergrizzlies.github.io/MegsCafe/`.
