# The Ashen Threshold

A small top-down souls-like that runs in the browser and installs to a phone's home
screen. The whole game — art, enemies, bosses — is one file: `index.html`.

**Live site:** https://dragonmahan-sketch.github.io/ashen-threshold/

## How this repository publishes

`index.html` and the three icons are pulled in when the site is built, by
`.github/workflows/pages.yml`, from the game's original home:

    https://the-ashen-threshold-vkpikx.freebuff.site

That is because the game is a single 145 KB file, larger than can be committed through
the tool that set this repository up. `sw.js` and `manifest.webmanifest` live here.

### To make the repository self-contained

1. Download `index.html`, `icon-192.png`, `icon-512.png` and `apple-touch-icon.png`
   from the live site above.
2. In this repository use **Add file → Upload files** and commit them at the top level.
3. Delete `.github/workflows/pages.yml`, then in **Settings → Pages** set
   **Source** to **Deploy from a branch**, branch **main**, folder **/ (root)**.

From then on GitHub serves the files exactly as they are, with no build step, and you
can edit `index.html` directly in the repository.

## On an iPhone

1. Open the live site in **Safari** and let it load into the game (five to ten seconds
   the first time).
2. **Share** → **Add to Home Screen** → **Add**.
3. Open it once from the new icon while online.

### Checking the offline copy is saved

Close the game, turn on **Airplane Mode**, then tap the icon again. If the game loads,
the offline copy is saved. If Safari says it can't open the page, reopen the site with
signal, wait ten seconds, and add it to the home screen again.

## Changing the game

After uploading a changed `index.html`, open `sw.js` and bump the version:

```js
const CACHE = 'ashen-threshold-v23';   // → v24, v25, ...
```

Otherwise a phone can keep showing its saved copy.
