# 2026 Careers Roadtrip — mobile web app

A self-contained, installable version of the road-trip pack. Host it on GitHub
Pages, open the link on your phone, and add it to your home screen so it opens
like a normal app (and works offline).

## Files in this folder
| File | Needed? | What it is |
|------|---------|------------|
| `index.html` | **yes** | The whole pack (fonts + images embedded, fully offline-capable) |
| `manifest.webmanifest` | **yes** | App name, colours, and icons for the home-screen app |
| `sw.js` | **yes** | Service worker, caches the pack so it works with no signal |
| `icon-180.png` | **yes** | Home-screen icon for iPhone/iPad |
| `icon-192.png` / `icon-512.png` | **yes** | Home-screen icons for Android / install prompts |
| `icon.svg` | optional | Source for the icon, only if you want to edit it later |

Keep all files together in the **same folder** (the repo root).

## 1. Put it on GitHub Pages
1. Create a new **public** repository on GitHub (e.g. `careers-roadtrip`).
2. Upload **all the files above** into it (drag-and-drop on the repo page →
   "commit changes"). Make sure `index.html` is at the top level, not in a
   sub-folder.
3. Go to the repo's **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**,
   pick branch **main** and folder **/ (root)**, then **Save**.
5. Wait ~1 minute, then refresh. Pages will show your live link, like:
   `https://YOUR-USERNAME.github.io/careers-roadtrip/`

That link is now shareable with the whole crew.

## 2. Add it to your home screen
Open the link in a **real browser** (this is also what makes the fonts render
correctly — previews inside Mail/Messages do not load embedded fonts).

**iPhone / iPad (Safari):**
1. Open the link in **Safari**.
2. Tap the **Share** button (square with an up-arrow).
3. Scroll down and tap **Add to Home Screen** → **Add**.

**Android (Chrome):**
1. Open the link in **Chrome**.
2. Tap the **⋮** menu (top right).
3. Tap **Add to Home screen** / **Install app** → **Install**.

It now appears as an app icon (the checkered flag) and opens full-screen with no
browser bars.

## 3. Offline
After you open it once, the service worker stores everything on the device, so
the pack keeps working even with no signal — handy on the South Coast.

## Updating the pack later
1. Replace `index.html` in the repo with the new version (commit the change).
2. Open `sw.js` and bump the cache name, e.g. change
   `const CACHE = 'careers-gp-v1';` to `'careers-gp-v2';`, and commit.
   This tells already-installed phones to pull the fresh version next time they
   open it online.
