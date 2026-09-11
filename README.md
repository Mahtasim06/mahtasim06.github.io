# Mahtasim's Portfolio — Deploy Guide (Polished Build)

Two pages, no build step:
- `index.html` — main portfolio
- `gallery.html` — one section per competition, club, and robot build
- `assets/` (not included here — see "What you need to supply" below)

This build is based on your own edited code. The only change made in this pass was a small CSS bug fix (below) — nothing else was altered.

## Copyright & Usage Restrictions

© 2026 Mahtasim Masrafi Chowdhury. All Rights Reserved.

This repository contains the source code, design, and personal content (photographs, achievement records, biographical information, and related data) of my personal portfolio website. **It is not open-source and is not licensed for reuse.**

Without my prior written permission, you may not:
- Copy, fork, or reuse any part of this code to build your own website, portfolio, or project
- Download, host elsewhere, or reuse any photographs, images, or logos from this repository or the live site
- Copy, scrape, or republish any of the biographical information, achievements, or other data shown here
- Use any part of this project's design, layout, or content as a template for your own work

Viewing this repository or the live website is fine for personal reference. Everything beyond that requires my consent.

See [`LICENSE`](./LICENSE) for the full legal notice.

To request permission for anything not covered above, contact: mahtasim.masrafi@gmail.com

## Fix applied in this pass

Your hero profile photo used a class called `square-full`, which isn't a real CSS class (Tailwind has no such utility), so it was silently ignored — meaning the photo container had no rounding at all and would display as a square instead of a circle. Changed both occurrences to `rounded-full`, which is the class your nav photo and everything else already correctly uses. No other lines were touched.

## What you need to supply

This handoff is just the two HTML files. For the site to display correctly, your `assets/` folder needs:
- `assets/Mahtasim_Masrafi_Chowdhury_CV.pdf`
- `assets/icon/favicon.png` (used for both the browser tab icon and your nav logo photo)
- `assets/profile/IMG_2500.jpg` (your hero photo)
- `assets/photos/` — all category photos (table below)
- `assets/logos/` — all organization badges (list below)

## Currently live gallery sections

| Category slug | Slots |
|---|---|
| `iccp-russia` | 15 |
| `bdro` | 6 |
| `bdbo` | 4 |
| `bdeo` | 11 |
| `bdmo` | 11 |
| `bdjso` | 4 |
| `boce` | 5 |
| `buet-robo-carnival` | 4 |
| `drmc-robotics-olympiad` | 3 |
| `sagc` | 5 |
| `aiub` | 6 |
| `bcic` | 6 |
| `drmc-tech-carnival` | 4 |
| `heritage-in-frames` | 2 |
| `mentors` | 5 |
| `math-club` | 9 |
| `ca` | 4 |
| `inter-math-olympiad` | 6 |

**Combined "Robots" section** — all of these render together under one `id="robots"` heading:

| Category slug | Slots |
|---|---|
| `robot-robosentinel` | 2 |
| `robot-robocurator` | 2 |
| `robot-patientpal` | 4 |
| `robot-phoenixecho` | 2 |
| `RC-Car-with-sensors` | 3 |
| `Surveillance-Car` | 2 |
| `Obstacle-avoiding-car` | 1 |
| `bluetooth-controlled-car` | 2 |
| `drilo` | 1 |
| `navigo` | 1 |
| `armify` | 2 |
| `tera` | 1 |
| `omega` | 1 |
| `hexa` | 1 |
| `hexa-omega` | 1 |
| `tera-omega-hexa` | 1 |
| `navigo-drilo-armify` | 1 |
| `Power-bank` | 2 |
| `Home-Automation` | 12 |
| `exp` | 7 |

Photo files are named `assets/photos/<slug>-<number>.jpg`.

**To add more photos to any category:** add the file as `assets/photos/<slug>-<next-number>.jpg`, then in `gallery.html` find that slug in the `groups` object (near the bottom of the file) and increase its number. That's the only change needed.

**To add a brand-new category:** add photos, copy an existing `<section>` block with a new `id`/`data-gallery` (or add the new slug into the `data-gallery-multi` list if it's another robot), and add its slug + count to `groups`.

## Currently disabled sections

These exist in `gallery.html` as HTML comments (not rendered, not in `groups`) — nothing was changed about them, just flagging they're there if you want to bring them back:
- `german-math-olympiad`
- `iymc`
- `olympiadians-hub`

Your homepage achievement cards for German Math Olympiad and IYMC currently link directly to `assets/gmo.jpg` / `assets/iymc.jpg` instead of these sections, so this is likely intentional.

## Logos in use

Every one of these needs to exist as a PNG in `assets/logos/`:

`iccp` · `gmo` · `iymc` · `boce` · `bdro` · `bdbo` · `bdeo` · `bdmo` · `bdjso` · `bcic` · `sagc` · `aiub` · `buet` · `drmcit` · `dicc` · `drmcsc` · `drmcmc` · `mentors` · `drmc` · `oxygen-robotics` · `olympiadians-hub` · `fca-math` · `me` · `jlrc`

## Going live on GitHub Pages

1. Create a GitHub repo named exactly `mahtasim06.github.io`.
2. Upload `index.html`, `gallery.html`, and your complete `assets/` folder.
3. Settings → Pages → Source: "Deploy from a branch" → `main` / `/ (root)` → Save.
4. Live in about a minute at `https://mahtasim06.github.io/`.

For getting found on Google searches of your name, see the indexing steps from the earlier guide (Search Console + "Request Indexing") — that part is unchanged and still applies.
