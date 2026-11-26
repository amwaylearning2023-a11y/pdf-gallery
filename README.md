# Nutrition W.I.S.E Programme – Module Library

A glassmorphism PDF gallery hosted on GitHub Pages. Each module card shows a first-page
preview, a **View** button (opens the PDF in a viewer) and a **Download** button (saves the PDF straight away).

## Files

| Path | What it is |
| --- | --- |
| `index.html` | The gallery page |
| `files.json` | The list of modules shown on the page |
| `pdfs/` | The module PDFs |

## Add or update a module

1. Upload the PDF to the `pdfs/` folder (**Add file → Upload files**), named `Module N - Title.pdf`.
2. Add an entry to `files.json`:
   ```json
   { "num": 7, "name": "Module 7 - Title", "file": "Module 7 - Title.pdf", "size": 1234567, "pages": 10 }
   ```
   `size` (bytes) and `pages` are only used for the label under each card.
3. Commit. The site updates in about a minute.

Add `"category": "Some Group"` to entries to get filter buttons at the top of the page.
