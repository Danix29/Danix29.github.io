# danix29.github.io

Personal portfolio site for **Daniel Del Nogal Buchanan** — Computer Engineering student at Universidad de Alcalá.

Live at → [danix29.github.io](https://danix29.github.io)

---

## Stack

| Layer | Choice | Reason |
|---|---|---|
| HTML | Single `index.html` | Zero build step, zero dependencies |
| CSS | Inline `<style>` block | Self-contained, no external stylesheet to cache-bust |
| JS | Inline `<script>` block | Same — one file is the whole site |
| Fonts | Google Fonts (JetBrains Mono + Syne) | Preconnect link, only two weights each |
| Hosting | GitHub Pages | Free, fast, custom domain ready |

No frameworks. No bundler. No npm. The entire site is **one HTML file + one SVG favicon**.

---

## Design

- **Color scheme:** dark green-black (`#0a0e0c`) base with a single teal accent (`#1D9E75`). All other colors are tints and shades of that one hue.
- **Typography:** [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) for body / code feel, [Syne](https://fonts.google.com/specimen/Syne) for headings and the name display.
- **Layout:** CSS Grid throughout — two-column about/contact, three-column stack grid, two-column projects grid. Collapses to single column below 768 px.
- **Language toggle:** EN / ES with `body.lang-en .es { display: none }` — no JS framework needed, one function call swaps the class.

---

## Sections

| # | Section | What's in it |
|---|---|---|
| — | Hero | Name, tagline, skill badges, terminal widget, CTA buttons |
| 01 | About | Bio paragraphs, 4-stat grid, language proficiency bars |
| 02 | Experience | Timeline — Base Aérea de Torrejón + Humanitas Bilingual School |
| 03 | Education | Timeline — UAH Computer Engineering + Bachillerato |
| 04 | Stack | 3-column skill bar grid (Languages / Tools / Concepts) |
| 05 | Projects | 2-column project cards with highlights and GitHub links |
| 06 | Interests | 3-column interest cards |
| 07 | Contact | Email, LinkedIn, GitHub, CV downloads, phone |

---

## Interactive features

All interactions are vanilla JS, implemented as isolated IIFEs inside the inline `<script>` block.

### Scroll
- **Progress bar** — 2 px teal line at the very top of the viewport, width tied to `scrollY / (scrollHeight - innerHeight)`.
- **Back-to-top button** — Fixed bottom-right, appears after scrolling 400 px, smooth-scrolls to top.
- **Fade-in on scroll** — `IntersectionObserver` adds `.visible` to `.fade-in` elements as they enter the viewport.

### Navigation
- **Active link highlight** — `scroll` listener finds the current section and colours the matching nav link teal.
- **Underline slide** — CSS `::after` pseudo-element on `.nav-links a` slides from `width: 0` to `width: 100%` on hover.
- **Mobile hamburger** — CSS-animated three-bar icon opens a full-width drawer below the nav.

### Hero
- **Particle canvas** — `<canvas>` injected as the first child of `#hero`. 55 teal dots drift at random velocities, wrapping at edges, rendered with `requestAnimationFrame`.
- **Terminal typewriter** — On load, the command and each output line type themselves out at 22 ms per character using `setInterval`.

### Cards
- **3D tilt** — `mousemove` on `.proj-card` and `.interest-card` computes `rotateX` / `rotateY` from cursor position relative to card centre, applied as a `perspective(600px)` transform.
- **Top-edge reveal** — CSS `::before` pseudo-element on `.proj-card` slides from `scaleX(0)` to `scaleX(1)` on hover.

### Buttons
- **Ripple** — `click` on `.btn` appends a `<span class="ripple">` at cursor position, animates `scale(0)` → `scale(140)` + `opacity 0`, then removes itself on `animationend`.

### Cursor
- **Glow** — A `position: fixed` radial-gradient `div` follows the cursor with lerp smoothing (`gx += (mx - gx) * 0.12` per frame). Grows to 80 px on hover over interactive elements.

### About section
- **Stat counters** — `IntersectionObserver` at 50 % threshold triggers a 1400 ms cubic ease-out counter animation on each `.stat-n` element.
- **Animated language bars** — Bars start at `width: 0%`; `IntersectionObserver` at 25 % threshold restores each bar's target width with a `70 ms` stagger.

### Stack section
- **Animated skill bars** — Same mechanism as language bars, watching the `#stack` section.

---

## File structure

```
Danix29.github.io/
├── index.html   ← entire site (HTML + CSS + JS, ~970 lines)
└── favicon.svg  ← teal "DN" monogram
```

---

## Meta / SEO

- `<meta name="description">` for search engines.
- Open Graph tags (`og:title`, `og:description`, `og:image`, `og:url`) for link previews on Slack, Discord, LinkedIn, etc.
- Twitter Card tags for X/Twitter unfurls.
- OG image generated dynamically via [capsule-render](https://github.com/kyechan99/capsule-render).

---

## Fonts loading strategy

```html
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700
            &family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
```

`display=swap` ensures text is visible with a system font while the custom fonts load — no invisible text flash.

---

## Local development

No build step required — just open the file:

```bash
# Option 1 — direct file
open index.html          # macOS
start index.html         # Windows

# Option 2 — local server (avoids any file:// quirks)
python -m http.server 8080
# then visit http://localhost:8080
```

---

## Deployment

Pushes to `main` deploy automatically via GitHub Pages. No CI/CD configuration needed — GitHub detects the repo name pattern `<username>.github.io` and serves it automatically.

```bash
git add index.html
git commit -m "your message"
git push origin main
# live in ~1–2 minutes at https://danix29.github.io
```
