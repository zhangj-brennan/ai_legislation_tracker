# AI Bill Tracker

## Data rule: always load live, never embed

The pages in `public/` must read their data from its source every time they load:

- `tracker.html` and `summary.html` load the published Google Sheet CSV.
- `definitions.html` loads the category definitions CSV that sits next to it in `public/`.

Never copy, convert or "generate" that data into the HTML or JS (no `const DATA = [...]`, no JSON snapshots, no build step that bakes in sheet contents). This applies even when it looks like a quick fix. If the data looks wrong, change how the page reads or displays the source, or ask. Don't paste in a corrected copy.

When a column, sheet or file name changes, update the page's loader (the `CSV_FILE` constant and the column names it reads). Don't replace the loader with a snapshot.
