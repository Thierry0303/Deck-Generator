# Deckhand
 
Turn notes, markdown or a rough outline into a designed presentation — and export it to
PowerPoint, PDF or a shareable web deck.
 
Everything runs in your browser. Nothing is uploaded, there is no account, and there is no
AI service behind it: the structure is worked out from the shape of what you write.
 
**[Try it](https://thierry0303.github.io/deck-generator/)** · no sign-up, no install
 
---
 
## Why
 
Most deck tools require an account and send your content to their servers. If you work with
anything confidential — client data, financial figures, anything under NDA — that makes them
unusable, whatever their features.
 
Deckhand is a single HTML file. Open it and it works, online or off.
 
## What it does
 
Paste your content, see the structure it detected, generate the deck, edit it inline, export.
 
It reads the **shape** of your text rather than guessing at meaning:
 
| You write | You get |
|---|---|
| `# Heading` | deck title, or a section divider |
| `## Heading` | a new slide |
| `- point` or `* point` | bullets (one or two columns, chosen by count) |
| `1. 2. 3.` | a numbered process |
| `Label: 99.97%` | metric cards |
| `\| a \| b \|` | a table, with numeric columns right-aligned |
| `> quoted line` | a statement slide |
| `### A` / `---` / `### B` | a side-by-side comparison |
 
Headingless notes work too — blank-line-separated chunks become slides.
 
Nine slide types, five themes. Long lists are split across slides in balanced pages, so you
never get a slide with one orphan bullet.
 
## Images
 
Drop or paste an image anywhere, or pick a file. Use it full-bleed, split beside text, or as
a cover behind a title slide. Images are downscaled on import and stored in IndexedDB **on
your machine** — they are never uploaded and never fetched from a remote host.
 
## Exports
 
- **PowerPoint** — a real `.pptx`, with native editable tables and embedded images
- **PDF** — through your browser's print dialog
- **Web deck** — a standalone HTML file you can send to anyone
- **Project file** — a self-contained `.json` holding the slides *and* their images, so a
  deck survives a new laptop
## Privacy, verified
 
The claim is testable, so it has been tested. Generating a deck, adding an image, cycling
every theme and running all three exports produces **zero requests that leave the machine** —
no fonts from a CDN, no analytics, no API:
 
```
total requests: 3
  GET document   file:///…/index.html
  GET image      data:image/jpeg;base64,…
  GET image      data:image/jpeg;base64,…
requests leaving the machine: 0
```
 
Check it yourself: disconnect from the internet and it still works.
 
## Running it
 
Download `index.html` and open it. That is the whole installation.
 
No build step, no dependencies to install, no server. PptxGenJS is bundled inside the file.
 
## How it works
 
One layout function per slide type emits positioned primitives in inches:
 
```
layoutSlide(slide, theme, env) → [ {k:'rect'…}, {k:'text'…}, {k:'image'…}, {k:'table'…} ]
                                    ↓                          ↓
                              renderDOM()                renderPPTX()
```
 
Neither renderer knows what a "metrics slide" is — they only draw rects, text, images and
tables. Even font size is decided upstream in the layout engine, from a shared character-width
model, rather than letting the browser and PowerPoint each guess at it.
 
That is why the preview matches the export: there is only one description of each slide, and
adding a slide type means writing one function rather than three.
 
Fonts are limited to faces that ship with Office on Windows and macOS. A webfont would look
better in the browser and then silently substitute on export.
 
## Limitations
 
- Desktop layout only — the editor is not yet responsive
- No image generation; you bring your own
- Fixed 16:9 slides, not expanding cards
## Licence
 
MIT
 
