# PDF Gallery

A glassmorphism gallery page for PDF modules, built as a Google Apps Script web app.
It lists every PDF in a Google Drive folder, with search, sorting, category filters
(from subfolder names), an in-page **View** preview and a one-click **Download** button.

## Files

| File | What it does |
| --- | --- |
| `Code.gs` | Server side: reads the Drive folder, caches the file list, setup and admin helpers |
| `Index.html` | The gallery page (glassmorphism UI, viewer modal, download links) |
| `appsscript.json` | Apps Script manifest (time zone, runtime, web app settings) |

## Setup

1. Create a new project at [script.google.com](https://script.google.com) and add `Code.gs` and an HTML file named `Index`.
2. Run `setup()` once. It creates a **PDF Gallery** folder in My Drive and links it to the app
   (or set `CONFIG.FOLDER_ID` to use an existing folder).
3. **Deploy → New deployment → Web app**, Execute as *Me*, choose who has access, then **Deploy**.
4. Upload PDFs to the folder. Subfolders become category filter chips.
5. Share the folder as **Anyone with the link → Viewer** so View and Download work without sign-in.

## Admin functions (run from the script editor)

- `standardizeNames()`: renames PDFs to `Module N - Title.pdf` and refreshes the list.
  Add titles for new modules in its `titles` map.
- `clearCache()`: makes new uploads show immediately instead of within 5 minutes.

After editing the code, publish it with **Deploy → Manage deployments → Edit → New version**
so the live link picks up the change.

## Settings (`CONFIG` in `Code.gs`)

- `FOLDER_ID`: Drive folder to list (leave as is to use the one from `setup()`)
- `TITLE`, `SUBTITLE`: page heading
- `CACHE_MINUTES`: how long the file list is cached (0 = always live)
