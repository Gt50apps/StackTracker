# Stack Tracker

Track the books you read and the audiobooks you listen to, on a 3D bookshelf.

- Shelf and list views, sorted and filtered by status
- Books with page progress; audiobooks as cassettes with time played and remaining
- Daily reading/listening log with a graph
- Customise each book: binding, cover, design, ribbon, page colour and edges; tapes get body, spinners and sticker colours
- Collections, stats, and backup/restore (Data tab)

Everything is stored in your browser on this device. Use **Data → Backup** to save a copy, and import it on another device or browser.

## Works offline

Nothing is loaded from the internet: Three.js is included (`three.min.js`) and the fonts are built into your device.
After the first visit, the service worker (`sw.js`) keeps a copy of every file, so the app opens with no connection.
It can also be installed to your home screen (browser menu → **Install app** / **Add to Home Screen**).

## Files

| File | What it is |
|---|---|
| `index.html` | the app |
| `three.min.js` | Three.js r128 (3D), bundled |
| `sw.js` | service worker: offline copy of the app |
| `manifest.webmanifest` | name, colours and icons for installing |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | app icons |
| `.nojekyll` | tells GitHub Pages to serve the files as they are |

## Host it on GitHub Pages

1. Create a repository and upload all the files above (keep them together in the root).
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, pick **Deploy from a branch**, choose `main` and `/ (root)`, and save.
4. After a minute the app is live at `https://<your-username>.github.io/<repository-name>/`.

## Updating

When you upload a new `index.html`, also change `VERSION` at the top of `sw.js` (for example `stack-tracker-v304`).
That tells installed copies to fetch the new files; they switch over the next time the app is opened.
