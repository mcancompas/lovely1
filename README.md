# Us — a slideshow

A single-page, dependency-free slideshow: full-screen photos with a slow
crossfade, background music, and drag-to-navigate. Built to drop straight
into GitHub Pages.

## Setup

1. Put your photos in the `images/` folder (any names/formats work — `.jpg`,
   `.png`, `.webp`...).
2. Put one song in the `music/` folder, named `song.mp3` (or update the
   `<source>` path in `index.html` if you'd rather keep your own filename).
3. Open `index.html` and edit the `SLIDES` list near the top of the
   `<script>` tag — one line per photo, in the order you want them shown.
   A caption is optional; leave it as `''` to show just the image.

```js
const SLIDES = [
  { src: 'images/1.jpg', caption: '' },
  { src: 'images/2.jpg', caption: 'Capri, 2022' },
];
```

4. Optionally change `AUTO_ADVANCE_MS` (how many milliseconds each photo
   stays up before advancing on its own — default 6500).

## Behavior

- Photos crossfade automatically on a timer.
- Dragging left/right on the image goes forward/back a slide and pauses
  the auto-advance timer for a bit (arrow keys work too).
- Music starts after the first tap (browsers block audio autoplay before
  any interaction) — the small note icon top-right mutes/unmutes.

## Deploying to GitHub Pages

1. Push this folder to a GitHub repo.
2. In the repo, go to **Settings → Pages**, set the source to your default
   branch (root), and save.
3. Your slideshow will be live at `https://<username>.github.io/<repo>/`.

## Notes

- No build step, no dependencies besides one Google Font (Cormorant
  Garamond) loaded over CDN — everything else is plain HTML/CSS/JS, so
  the page stays fast and light.
- Large photo files will slow the first load — resizing images to roughly
  1600–2000px on the long edge before uploading keeps things snappy.
