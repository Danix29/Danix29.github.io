# danix29.github.io

Personal portfolio site for **Daniel Del Nogal Buchanan**, Computer Engineering student at Universidad de Alcalá (Year 3).

Live at → [danix29.github.io](https://danix29.github.io)

---

## Stack

| Layer | Choice | Reason |
|---|---|---|
| HTML | Single `index.html` | Zero build step, zero dependencies |
| CSS | Inline `<style>` block | Self-contained, no external stylesheet to cache-bust |
| JS | Inline `<script>` block | Same: one file is the whole site |
| Fonts | Google Fonts (Archivo + JetBrains Mono) | Preconnect, `display=swap` |
| Hosting | GitHub Pages | Free, fast, deploys on push |

No frameworks. No bundler. No npm. The entire site is **one HTML file + one SVG favicon**.

---

## Design — Industrial brutalism / tactical telemetry

Redesigned in October 2026.

- **Palette:** carbon `#0B0B0B` substrate, phosphor-white ink `#EAEAEA`, aviation red `#FF2A2A` as the only accent. Terminal green `#4AF626` is used for exactly one element (the "open to internships" status light).
- **Light theme:** Swiss-print variant: unbleached paper `#EAE8E3`, carbon ink, hazard red `#E61919`.
- **Typography:** [Archivo](https://fonts.google.com/specimen/Archivo) 900 for uppercase macro headings (tight tracking, ~0.84 leading), [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) for every piece of metadata, Archivo 400–600 for body copy.
- **Geometry:** `border-radius: 0` everywhere. Compartments are drawn with the `gap: 2px` + ink-coloured parent trick, so dividing lines are pixel-exact without per-cell borders.
- **Texture:** fixed blueprint grid, CRT scanlines and an SVG noise layer.
- **Motion:** stepped (`steps()`) timing everywhere, so things move like machinery rather than easing.
- **Language toggle:** EN / ES via `html.lang-en .es { display: none }`, persisted in `localStorage`.

---

## Sections

| # | Section | What's in it |
|---|---|---|
| — | Intro | Boot sequence: terminal log, 000→100 % counter, segmented load bar, slatted exit |
| — | Hero | Name block, telemetry metadata row, typed terminal, `<dl>` readout, CTAs, barcode |
| 01 | About | Bio, 4-stat compartment grid, segmented language meters |
| 02 | Stack | Skill radar (canvas) + 3 columns of segmented meters |
| — | Statement | Scroll-scrubbed manifesto line |
| 03 | Projects | Gapless 6-column grid, filters, cards invert on hover |
| 04 | Interests | 6 compartment cards with square icon plates |
| 05 | Experience | Log-style entries (`JOB-01 // STATUS: ACTIVE`) with numbered bullets |
| 06 | Education | "Currently" banner, degree + 2026–27 enrolment (12 subjects, 78 ECTS), Fortinet NSE 1–3, Bachillerato, ESO, Cumlaude, extension course, English C1+ |
| 07 | Contact | Oversized CTA headline + link table (email, GitHub, LinkedIn, CVs, phone) |

---

## Interactive features

All vanilla JS, isolated in one IIFE inside the inline `<script>`.

- **Boot intro** — plays on load (~2.5 s). Skip with click, `Esc`, `Enter` or `Space`. Skipped entirely under `prefers-reduced-motion`, and a CSS failsafe hides it after 8 s if JS ever fails.
- **Scroll engine** — one rAF-throttled passive listener drives the red progress bar, the active nav link, the back-to-top button and the word-by-word statement scrub.
- **Shutter reveals** — `IntersectionObserver` retracts a solid mask over each block in 6 mechanical steps.
- **Hero canvas** — square "pixel" particles; paused when the hero is off-screen.
- **Terminal typewriter** — starts after the intro finishes.
- **Counters and meters** — stepped counters, segmented meters that fill on first view.
- **Skill radar** — canvas, redraws on theme/language change.
- **Project filters** — Java / Python / SQL / C / Web; the grid re-flows to stay gapless.
- **Keyboard** — `?` shortcuts, `g` + letter to jump to a section, `t` theme, `l` language. Plus a Konami code.

---

## File structure

```
Danix29.github.io/
├── index.html   ← entire site (HTML + CSS + JS)
├── favicon.svg  ← black/white "DN" plate with a red band
└── README.md
```

---

## Meta / SEO

- `<meta name="description">`, Open Graph and Twitter Card tags.
- OG image generated with [capsule-render](https://github.com/kyechan99/capsule-render) in the site palette.

---

## Analytics

| Tool | What it tracks | Dashboard |
|---|---|---|
| [GoatCounter](https://www.goatcounter.com) | Page views, referrers, country, browser — no cookies, GDPR-friendly | [danieldelnogal.goatcounter.com](https://danieldelnogal.goatcounter.com) |
| [Microsoft Clarity](https://clarity.microsoft.com) | Session recordings, heatmaps, scroll depth | [clarity.microsoft.com/projects/view/x1daajnt6w](https://clarity.microsoft.com/projects/view/x1daajnt6w) |

Both load asynchronously.

---

## Local development

```bash
python -m http.server 8080
# then visit http://localhost:8080
```

## Deployment

Pushes to `main` deploy automatically via GitHub Pages (live in ~1–2 minutes).
