# Review Deck Builder

A standalone, single-file web tool that speeds up building the **Monthly Service
Review** and **Quarterly Business Review (QBR)** decks. Fill in a series of
fields each month, toggle slides on/off, add or remove slides, and export a
native **PowerPoint (.pptx)** file styled in the Outseer brand.

## How to use

1. Open **`index.html`** in any modern browser (double-click the file, or
   drag it into a browser tab). No install or server needed.
2. Pick a starting template at the top — **Monthly Review** or **QBR**. Each
   loads a ready-made slide sequence pre-filled with example content.
3. Work through the slide list on the left:
   - Click a slide to edit its fields on the right; the preview updates live.
   - Use the **toggle** on each slide to include or skip it in the export.
   - **Drag** slides to reorder, or use **Duplicate** / **Delete**.
   - **Add slide** to insert any block type (title, agenda, divider, bullets,
     KPI cards, table, chart, closing).
4. Click **Download PPTX** to generate the PowerPoint. Skipped slides are
   left out and page numbers renumber automatically.

## Saving your work

- **Save** downloads a `.json` file with everything you've entered.
- **Open** loads a `.json` file back in — so next month you can start from
  last month's deck and just update the numbers.
- Your work is also auto-saved in the browser (local storage) between visits.

## Monthly workflow — carry last month forward

You don't start from scratch each month:

1. **Upload last review** — click it and pick either last month's saved `.json`
   **or last month's PowerPoint that this tool produced**. Every `.pptx` the tool
   exports carries its data invisibly inside the file, so re-uploading it
   restores the whole deck exactly.
2. The **Monthly update** panel opens automatically. Set the new reporting
   month and type only the values that changed:
   - each **12-month trend** chart (SLA, DDoS, case volumes) rolls its window
     forward one month and asks for the new month's value (last month's value is
     shown for reference);
   - **KPI cards** show their current figures to overwrite.
3. Click **Apply updates**, review, then **Download PPTX**.

You can reopen the Monthly update panel any time from the toolbar.

### Importing a hand-made deck (best-effort)

You can also upload a PowerPoint that was **not** made by this tool. The tool
reads titles, tables and chart data to give you a starting point — but because
hand-built decks vary, this is best-effort: **check every value** after import.
Decks made by this tool always restore perfectly.

## Slide types

| Type | Use for |
|------|---------|
| Title / Cover | Client, deck title, period, date, presenters |
| Agenda | Numbered list of topics |
| Section Divider | Full-bleed section breaks |
| Bulleted Content | Title, lead line and bullet points |
| KPI / Stat Cards | Headline + metric cards + "what this means" (e.g. DDoS summary) |
| Table | Any grid — attendees, actions log, SLA summary, peer comparison |
| Chart | Column, stacked, bar, line, pie or doughnut with editable data |
| Closing | Thank-you / sign-off |

## Notes

- **Works fully offline.** The PowerPoint engine (PptxGenJS) and zip library
  (JSZip) are bundled inside `index.html`, so it works with no internet and on
  networks that block external scripts. Nothing you enter leaves your machine.
  (Fonts are the only online extra; without a connection the tool falls back to
  system fonts — everything still works.)
- Charts are exported as **native, editable PowerPoint charts**, and tables as
  real tables, so you can fine-tune them in PowerPoint afterwards.
