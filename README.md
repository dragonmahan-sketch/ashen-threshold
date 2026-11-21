# The Ashen Threshold

A small top-down souls-like that runs in a browser and installs to a phone's home
screen. Everything — the art, the enemies, the bosses — is in one file: `index.html`.

## What is in this folder

| File | What it is |
| --- | --- |
| `index.html` | the whole game |
| `sw.js` | the offline cache, so it works with no signal |
| `manifest.webmanifest` | the name, colours and icons the phone uses |
| `icon-192.png`, `icon-512.png` | home-screen icons |
| `apple-touch-icon.png` | the icon iPhone uses |

## Play it on a computer

Double-click `index.html`. It opens in your browser and plays straight away.
(The offline part only works on a real web address, not from a local file — that is normal.)

## Put it online with GitHub Pages (free)

1. Sign in at github.com and click **New repository**.
2. Name it something like `ashen-threshold`, leave it **Public**, click **Create repository**.
3. On the new page click **Add file → Upload files**, drag **every file in this folder**
   into the window (file and folder names must stay exactly as they are, all at the top
   level — do not put them inside another folder), then click **Commit changes**.
4. Go to **Settings → Pages**. Under **Source** choose **Deploy from a branch**,
   then Branch: **main**, folder: **/ (root)**, and click **Save**.
5. Wait a minute or two, reload the Settings → Pages page. Your game will be at:
   `https://YOUR-USERNAME.github.io/ashen-threshold/`

If that address shows "404" at first, it just means GitHub is still building it —
reload after another minute.

## Put it on an iPhone home screen

The game tells you this itself: the first time it opens in Safari, the start screen
shows the three steps below plus the no-signal test. Press **H** on a keyboard to bring
that screen back.

Use **Safari** for this. Chrome on iPhone cannot add web apps to the home screen properly.

1. Open Safari and go to your address, e.g.
   `https://YOUR-USERNAME.github.io/ashen-threshold/`
2. Let it load all the way into the game — you should see the burning bonfire in the
   hall. Give it five to ten seconds on that first visit: the offline files are saved
   while the page sits there.
3. Tap the **Share** button at the bottom of the screen (a square with an arrow coming
   out of the top).
4. In the sheet that slides up, scroll down and tap **Add to Home Screen**.
5. Name it whatever you like — "Ashen" is what the game asks for — and tap **Add**.

Now tap the new icon on your home screen (not Safari) once while you are still online,
let the game appear, and play for a few seconds. That first launch from the icon is what
finishes setting up the standalone app and its offline files.

On Android the same idea works in Chrome: menu (three dots) → **Add to Home screen**.

## Checking the offline copy is really saved

1. With the game open from its home-screen icon, close it by swiping up from the bottom
   of the screen.
2. Turn on **Airplane Mode**: swipe down from the top-right corner for Control Centre
   and tap the plane icon.
3. Tap the game icon again.

- **The game loads and plays** → the offline copy is saved, and you are done. Turn
  Airplane Mode back off.
- **A page says Safari cannot open the page because the iPhone is not connected to the
  internet** → it was not saved yet. The usual cause is that the first visit, or the
  first launch from the icon, did not finish.

To fix that: turn Airplane Mode off, delete the home-screen icon, open the address in
Safari again, wait a good ten seconds on the game, then add it to the home screen again
and launch it once from the icon while online.

## Good to know

- The saved copy only refreshes when you open the game **while online**. After you
  upload a changed game, open it once with signal.
- iOS can clear saved offline data for apps it has not used in a long time, or when the
  phone is very low on storage. One online open fixes it.

## Changing the game

Open `index.html` in any text editor. Code, colours, enemy numbers and level layout are
all inside it.

When you upload a changed game, also open `sw.js` and change the version line:

```js
const CACHE = 'ashen-threshold-v24';   // → v25, v26, ...
```

That tells phones to throw away their saved copy and download the new one. Without it
a phone can keep showing the old version.
