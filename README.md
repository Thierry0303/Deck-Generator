# Deck Updater

A single-file web tool that opens your PowerPoint, turns its content into
editable fields, and lets you produce the next version **without changing the
design**. Everything runs in your browser — nothing is uploaded anywhere.

Ideal for a recurring monthly/quarterly review: open last period's deck, update
the numbers, add or remove a slide, download the new deck.

## How to use

1. Open **`index.html`** in any modern browser (double-click it).
2. **Open .pptx** — choose your presentation (or drag it onto the page).
3. The left panel lists every slide. Click one to edit its content on the right:
   - **Text** — titles, bullets and paragraphs.
   - **Tables** — every cell.
   - **Charts** — series names, category labels and each value.
4. **Add month** (top bar) — appends this period's figures to every chart in one
   step: type the new label (e.g. "Sep 26") and each series' latest value.
5. **Duplicate** / **Delete** slides from the left panel, and drag to reorder.
6. **Download .pptx** — writes your edits back into the original file and saves
   `<name>_updated.pptx`. The master, layouts, fonts, logos, images and styling
   are all preserved exactly, because the tool edits your file in place rather
   than rebuilding it.

## Notes

- Works fully offline — the zip engine is bundled inside `index.html`.
- Editing a paragraph keeps the formatting of its first run.
- Duplicated slides get independent copies of their charts, so editing one does
  not change the other.
- There is no in-app visual preview (the styled result lives in PowerPoint) —
  download to see the finished slides.
