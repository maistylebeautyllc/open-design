# Mai Style Beauty — promo videos

Short vertical (1080×1920, 24 fps, 30 s) promo films for Mai Style Beauty, drawn entirely in code in the
**Art Deco** style from [Lemo-Opuscar](https://github.com/lemomo-ai/lemo-opuscar) (MIT). No video model,
no stock footage; the music and sound effects are synthesised in `score.py`.

This folder is **not part of the OpenDesign product**. The source is kept as `project.tar.gz` so its
JavaScript doesn't trip the repo's `pnpm guard` TypeScript-only check.

## Videos

| File | What |
|---|---|
| `videos/2026-11-main-promo.mp4` | Main promo: five services behind five Art Deco doors, bulb marquee, "Book your appointment" |

## Services shown

Hair styling & color · Hair extensions · Makeup & skincare · Teeth whitening · Body sculpting

## Rebuild or make a new version (e.g. a holiday edition)

```sh
mkdir -p /tmp/mai && tar xzf promo-videos/mai-style-beauty/project.tar.gz -C /tmp/mai && cd /tmp/mai
sh build.sh        # → mai-style-beauty-promo.mp4 + poster.jpg  (~5 min)
```

Needs `node` with Playwright's Chromium (`render.mjs` imports it from `/opt/node-tools/node_modules/playwright`;
adjust that path if needed), `python3` + `numpy`, and `ffmpeg`.

What to edit for a new version:
- **`film.js`**: `SERVICES` (titles, sub-lines, icons), the opening line (`'YOUR GLOW-UP'`), the marquee text
  (`LINE1`/`LINE2`), the closing banner and line, and colours (`ROSE` is the one accent colour; `EMER` the jewel tone).
  Timings: `SERV_T0`, `SERV_LEN`, `BREATH`, `MARQ_T0`, `CTA_T0`. Keep `score.py`'s door and marquee times in step.
- **`score.py`**: chords (`CH`), walking bass (`WALK`), tempo (`BEAT`), and the sound cues.
- Style rules to keep: warm black + gold + ivory, one accent colour, everything symmetric on the centre axis,
  transitions are doors splitting on the centre seam. Keep text above y≈1550 (Reels captions cover the bottom).
- Check stills first: `node render.mjs stills 2 6 13 28` → `out/stills/`.

After building, copy the new mp4 + poster into `videos/` with a dated name and add a row to the table above.
Pack edited source back with
`tar czf project.tar.gz TREATMENT.md CREDITS build.sh film.js index.html render.mjs score.py engine fonts`.

## Holiday editions

The owner wants a holiday edition for every holiday: US/world holidays, cultural holidays (including
**Hmong New Year**, Lunar New Year, Eid, Diwali, Juneteenth) and beauty seasons (prom, weddings,
back-to-school, summer). A scheduled reminder asks before each one; a video is made only once the owner says go.
