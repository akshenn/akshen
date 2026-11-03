# Akshen Sivakumar — Portfolio

A one-page portfolio site (Home, SPUR Fashion Show, Reverie, EliteMD, Social media recap, Contact).
No build step: open `index.html` in a browser to preview it.

```
index.html     the whole site: layout, styles, scripts and the SITE settings
media/         every photo, video and sound the site uses (and nothing else)
_originals/    raw .mov / .heic files and backups; stays on your computer, not uploaded
```

## Editing content

Everything you'd swap lives in the **SITE settings** near the bottom of `index.html` (search `const SITE`).
Each slot takes one of:

| Value | Shows |
|---|---|
| `"media/photo.jpg"` | an image |
| `"media/clip.mp4"` | a video (muted, looped) |
| an Instagram / TikTok / YouTube / Vimeo link | that platform's player |
| `""` | nothing (or a dashed prompt box when `draft: true`) |

- `draft: false` hides empty slots (set for publishing). Switch to `true` while editing to see where things go.
- `CANVA + "..."` links load from akshen.my.canva.site and only work while that Canva site stays published.
- Videos: export MP4 (H.264), under ~15 MB each. Keep file names lowercase with no spaces.
- `reverie.mp4` and `las-vegas.mp4` play full screen; if either file is missing, the Instagram version shows instead.
- EliteMD: `elitemd.materials[0]` sits beside the intro; `elitemd.more` holds the row of three tall tiles.

## Password gate

`window.GATE = "fidelio";` near the top of `index.html`. Set it to `""` to turn the gate off.
It's a styled entrance, not security: the word is shown on screen and visible in the code.
Gate music: `media/fidelio-loop.mp3`, with `media/fidelio.MP3` as backup (keep the capital `.MP3` exactly).
The typewriter, power-on and cha-ching sounds are built into `index.html`; volumes are in `const VOL`.

## Other options (SITE settings)

- `sound.tryAutoplayWithSound` / `sound.unmuteOnFirstTap`: how the films try to start with sound
- `scroll`: `"free"` or `"snap"`
- `alternate`: `true` alternates the image side down the page

## Publishing

**GitHub Pages:** push this folder to a GitHub repository, then Settings → Pages → Deploy from branch → `main` / root.
`.gitignore` keeps `_originals/`, `.DS_Store` and private notes out of the upload.

**GoDaddy cPanel:** upload `index.html` and the `media` folder into `public_html`.
