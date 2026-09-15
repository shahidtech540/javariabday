# 🎂 Javaria turns 19 — birthday site

One single file: **`index.html`**. No build step, no dependencies, no frameworks.
Open it in a browser, or drop it on any static host (Netlify, GitHub Pages, your phone).

Everything you need to personalise is below. Total time: ~5 minutes.

---

## 1 · Set her birthday (10 seconds)

Open `index.html`, scroll to the bottom `<script>` tag, find the **CONFIG** block:

```js
const CONFIG = {
  birthday: "2026-09-16",   // ← YYYY-MM-DD  (the page counts down to midnight starting this day)
  song: "/audio/song.mp3",  // ← path to her song
  songName: "Her favourite song", // ← label shown in the mini player
};
```

- Opened **before** the date → live countdown to midnight.
- Opened **on** the date → "IT'S HER DAY!" mode + the full-screen confetti reveal.
- Opened **after** the date → it automatically rolls the countdown to next year
  (and still shows the celebration mode on the day itself).

## 2 · The gallery wall (section 02)
Real photos are WIRED: `images/gal01.jpg` … `gal05.jpg` (masonry collage,
tilted prints, no captions). To swap a photo, replace the file keeping the
name — or edit the `<img src>` inside the matching `<!-- PHOTO n -->` card.
Add/remove `<article class="card reveal">` blocks freely; the wall reflows.

## 3 · Write the letter (2 minutes)

Search for `id="letterBody"`. Replace the four `[bracketed paragraphs]` with your own
words. Keep them inside `<p>` tags inside `.letter-body` — the word-by-word
typewriter reveal adapts automatically to whatever you write, however long it is.

The sign-off line ("— Your brother ♥") is the `.signoff` div right below.

She never sees the letter raw: section 04 now shows a **sealed envelope** with a wax
"J" seal. Tapping it (or the "Open the envelope" button) pops the seal, flips the
flap, lifts the letter out, fires **fireworks + blooming flowers**, and only then
blooms the letter card in with the typewriter reveal. Nothing to configure — it's
all automatic, and it respects `prefers-reduced-motion`.

## 4 · Add her song (30 seconds)

Drop an `.mp3` next to the file, e.g. `audio/song.mp3`, then either:

- set `song: "audio/song.mp3"` in the CONFIG block, **or**
- edit the `<source src="/audio/song.mp3">` tag in the player markup (search `REPLACE THIS SRC`).

The player starts silent and only makes sound after she taps the ▶ pill
(browsers block autoplay). Volume fades in gently, loops, and the bar is tappable to seek.

---

## Nice-to-knows

| Thing | Where |
|---|---|
| Colour palette | `:root` CSS variables at the top (`--pink`, `--orange`, `--cream`, `--lime`, `--plum`) |
| Fonts | Google Fonts `<link>` in `<head>` (Bricolage Grotesque + DM Sans). Offline? It falls back gracefully. |
| Marquee text | the `.ribbon` block near the top |
| Balloon surprise messages | the `MESSAGES` array in the script |
| Hero one-liner | the `<p class="lede">` in the hero |
| Closing line | section `05 — The last page` |

**Easter eggs built in:** tap the 🎈 button for balloons + a message, and tap the
"19th" chip in the headline for a secret confetti pop.

**Tested:** Chrome (desktop 1440px + mobile 390px), no console errors, no horizontal
scroll, respects `prefers-reduced-motion`.
