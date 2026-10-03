# paper

A poster for one page. One plate, a title, a verse, a colophon.

`paper` is a single sheet: a portrait figure takes the top, a title and a
verse sit in two columns under it, and a date and a barcode close the page.
It is meant to be the front of something — a home page with the navigation
not yet added. Everything on it is a token, so the next pass changes the
words and the figure without touching the frame.

## What is on it

- **The plate.** A 4:5 portrait frame (the reference photograph is 528×661
  on a 720×1280 story). Today it holds a painted placeholder because there
  is no photograph yet; `background-image` on `.plate` is the one line to
  change when there is.
- **The stack.** Two columns sharing a top edge: a title at 600 on the left,
  the verse answering on the right. The verse is taller and continues past
  the title. They do not share a last baseline.
- **The colophon.** A date and a credit on the left; a barcode and a weekday
  on the right. No hairline — the page closes on white space.

## Type

Jost, self-hosted, three subset files (latin, latin-ext, italic) — 55 KB
before compression. 600 carries the title and every label, 400 carries the
verse. Nothing depends on a third party at runtime.

Ume green is the only hue and it stays on words: the title (`--word`, a dark
forest measured off the reference), the focus ring, the selection. Surfaces
are white and the plate's own colour.

## Files

```text
/
├── index.html
├── contact.html       # a board of two mail doors
├── public/
│   ├── favicon.svg
│   └── fonts/
└── src/
    ├── tokens.css     # every colour, size, and distance on the page
    ├── fonts.css      # @font-face + unicode ranges
    ├── poster.css     # the layout
    └── contact.css    # the contact board
```

## Running it

Any static server from the repo root:

```bash
python3 -m http.server 4400 --bind 0.0.0.0
```

No build step, no dependencies, no framework. Substitution values live in
`src/tokens.css`; the wording lives in `index.html`.
