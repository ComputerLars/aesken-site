# Kunstrum ÆSKEN — website

A living collage of everything ÆSKEN has posted. The whole feed drifts and
mutates like one organism; you can drag and tap every image, open the videos,
and float the program/archive boxes around the screen.

It is plain HTML/CSS/JS — **no build step, no dependencies**. It runs as a static
site (e.g. GitHub Pages).

---

## Files

| File / folder | What it is |
|---|---|
| `index.html` | The whole site (layout + motion + interaction). |
| `media.js`   | **The list of images & videos.** ← edit this to add media. |
| `data.js`    | The text content (Program strands + Archive entries). |
| `img/feed/`  | The actual image & video files. |

All four must be present together.

---

## Add more images or videos

Two steps:

1. **Put the file** into the `img/feed/` folder (`.jpg`, `.png`, or `.mp4`).
2. **Add its filename** to the list in `media.js`:

```js
window.MEDIA_FILES = [
  "17848257267524279.jpg",
  "my-new-photo.jpg",     // ← add a line like this
  "my-new-clip.mp4",      // ← videos work the same way
];
```

That's it. Videos (`.mp4`) are detected automatically — they get a ▶ mark, play
when opened, and join the ambient sound track. The order in the list doesn't
matter; the wall shuffles itself.

> Tip: any filename works, but keeping the original Instagram IDs (or short
> names without spaces) is safest.

---

## Put it online / update the live site

### If you use the command line

```bash
git add .
git commit -m "Add new photos"
git push
```

GitHub Pages rebuilds automatically — the site updates in about a minute.

### If you prefer the GitHub website (no terminal — anyone can do this)

1. Open your repository on github.com.
2. Go into the `img/feed` folder → **Add file ▸ Upload files** → drag your new
   image/video in → **Commit changes**.
3. Open `media.js` → click the ✏️ (Edit) button → add a line with your new
   filename (see example above) → **Commit changes**.

Done. The live site updates by itself.

---

## Notes

- **Sound:** browsers only allow audio after the first click/tap, so the
  ambient "mumble" of the videos starts as soon as you touch the page, then
  cycles through the clips forever at a low volume.
- **Motion:** respects the system "reduce motion" setting — it goes calm/still
  for visitors who ask for that.
- Nothing is tracked or counted; there is deliberately no "X images" number
  anywhere.
