# Meg's Café

Single-page marketing site for **Meg's Café** — a tiny home-based café in
Gilbert, Arizona. Hand-pulled lattes, hot or iced, ordered ahead and picked up
at the front-porch counter. Open Mon–Sat, 7am–1pm (closed Sundays).

Plain HTML/CSS/JS in one file. **No build step, no dependencies** — open
`index.html` in a browser.

> **Handoff note:** working notes for an AI assistant (design tokens,
> conventions, the poster-editing recipe, open TODOs) live in
> [`CLAUDE.md`](CLAUDE.md).

## Status

Design and copy are done. The current site is a clean, minimal layout (modeled
on the Hunnybee Bruncheonette look) after earlier, busier designs were rejected.
**Two things still need a human:**

1. **Hotplate link** — the "Order on Hotplate" button is a placeholder. Hotplate
   handles ordering + pickup scheduling + payment; the shop hasn't been created
   yet. Replace `https://www.hotplate.com/` in `index.html` (search for the
   `TODO` comment) once the store exists.
2. **Social handles** — Instagram `@cottagecafe` and email
   `hello@cottagecafe.com` are legacy "Cottage Cafe" branding and don't match
   the new name. Update when the real handles are known.

## Structure

- `index.html` — the site. Sections: **Home · Menu · Order · About** (single
  page, anchor nav with scroll-spy highlighting).
- `latteart.jpg` — hero poster (green botanical latte-art print, re-lettered to
  "Meg's Café").
- `latteart.original.jpg` — the original poster ("Meghan's Little Cafe") before
  re-lettering.
- `logo.png` — hand-drawn cottage logo (still reads "Cottage Cafe"; **not** used
  on the current site).
- `espresso.png` — espresso-machine illustration (not used on the current site).
- `index.riso.html` — the previous, much busier "risograph" design, kept for
  reference. The owner rejected this direction.
- `index.backup.html`, `candidates/` — older drafts and four design candidates.

## Menu (source of truth is `index.html`)

Five lattes, hot or iced, same price either way:

| Latte | Price |
| --- | --- |
| Honey Lavender | $5.50 |
| Brown Sugar Cinnamon | $5.50 |
| Vanilla Bean | $5.25 |
| Salted Caramel | $5.50 |
| Classic | $4.50 |

Customizations: milk (whole / oat +$0.75 / almond +$0.75), flavors (vanilla,
caramel, lavender, hazelnut, brown sugar — 1–4 pumps), espresso (extra shot +$1,
decaf). Baked goods are advertised as "coming soon."

## Next steps

1. Create the Hotplate shop and drop its URL into the "Order on Hotplate" button.
2. Update Instagram / email handles to match "Meg's Café."
3. Confirm the name spelling — the site uses **"Café"** with the accent. If it
   should be plain "Cafe," update both `index.html` and the poster
   (`latteart.jpg`). See `CLAUDE.md` for how to re-letter the poster.
4. *(Optional)* Publish via **GitHub Pages**: repo Settings → Pages → Source:
   `main` / root → site goes live at
   `https://vancouvergrizzlies.github.io/MegsCafe/`.
5. *(Optional)* Delete the reference files (`index.riso.html`,
   `index.backup.html`, `candidates/`, `latteart.original.jpg`) for a clean repo.
6. Add real baked-goods items when ready.

## Local preview

Open `index.html` in any browser, or serve it:

```sh
python3 -m http.server   # then visit http://localhost:8000
```
