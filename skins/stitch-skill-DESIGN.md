# Design System: Daniel Del Nogal Buchanan, Portfolio

## 1. Visual Theme & Atmosphere
A calm, daily-app-balanced portfolio (Density 4) with confident offset-asymmetric
layouts (Variance 7) and fluid, spring-weighted motion (Motion 6). The mood is
"well-lit engineering lab": clinical surfaces, generous air, one cool teal signal
that marks everything you can act on. The page should read like a careful
engineer wrote it, not like a template. Photography is real, desaturated and
small: it punctuates the type instead of competing with it.

## 2. Color Palette & Roles
- **Lab Canvas** (#F7F8F8) — page background, light theme
- **Pure Surface** (#FFFFFF) — cards and elevated containers
- **Graphite Ink** (#18181B) — primary text, Zinc-950 depth
- **Muted Steel** (#5F6368) — secondary text, descriptions, metadata
- **Whisper Border** (rgba(24,24,27,0.08)) — 1px structural lines, card borders
- **Signal Teal** (#0F766E) — the single accent: primary CTA, focus rings, active filters, highlights
- **Night Canvas** (#0C0F0F) / **Night Surface** (#151A1A) / **Night Ink** (#ECEFEE) / **Night Teal** (#2DD4BF) — dark theme equivalents
Max one accent. Saturation stays below 80%. No purple, no neon, no pure black (#000000).

## 3. Typography Rules
- **Display:** Satoshi 700, track-tight (-0.04em), controlled scale `clamp(2.6rem, 6vw, 5.4rem)`. Hierarchy comes from weight and color before size.
- **Body:** Satoshi 400/500, relaxed leading (1.65), max 65 characters per line, Muted Steel for secondary copy.
- **Mono:** JetBrains Mono for dates, numbers, counts, file names and metadata.
- **Accent serif:** Instrument Serif italic, only for one emphasised word per headline. Never for body.
- **Banned:** Inter, Times New Roman, Georgia, Garamond, Palatino.

## 4. Hero
- **Inline image typography is the signature move:** two small, contextual photos sit inside the headline at type height, fully rounded, acting as punctuation ("Software that [photo] holds up [photo] under pressure").
- Left-aligned, asymmetric: headline across ~8 of 12 columns, a quiet facts column on the right. Nothing overlaps.
- Exactly one primary CTA ("Email me"). No secondary "Learn more" link.
- No scroll cues, no bouncing chevrons, no "Scroll to explore".
- On mobile the inline photos stack under the headline as a small row.

## 5. Component Stylings
* **Buttons:** Signal Teal fill, white label, generously rounded (14px). No outer glow. Tactile -1px translate and 0.98 scale on press.
* **Cards:** Generously rounded corners (2.5rem), Pure Surface fill, Whisper Border, diffused whisper shadow (0 20px 40px -15px rgba(0,0,0,0.05)). Used only when elevation communicates hierarchy; lists use border-top dividers instead.
* **Filters:** Segmented pills; the active pill takes the Signal Teal fill.
* **Tags:** Small, soft-rounded, Whisper Border, mono text.
* **Loaders:** Skeletal shimmer matching each image's exact aspect ratio. No circular spinners.
* **Empty states:** If a filter returns nothing, show a composed message explaining how to widen the filter.

## 6. Layout Principles
Grid-first, max-width 1400px centered. Offset asymmetry everywhere: 8/4 hero split,
2fr/1fr project grid, alternating zig-zag for interests (never more than two in a row),
a border-top list for experience. No 3-equal-card rows. No flexbox percentage math.
Full-height hero uses min-height: 100dvh. Everything collapses to one column below 768px,
with no horizontal scroll and 44px minimum tap targets. Section gaps use clamp(3rem, 8vw, 6rem).

## 7. Motion & Interaction
Spring-weighted easing for every interactive element (stiffness 100 / damping 20, approximated
in CSS as cubic-bezier(0.22, 1, 0.36, 1)). Staggered cascade reveals (90ms steps) as sections
enter. Perpetual micro-loops only where they mean something: the availability pulse, a slow float
on the hero's inline photos, the shimmer while images load. Transform and opacity only.
Grain lives on a fixed, pointer-events-none layer.

## 8. Anti-Patterns (Banned)
- No emojis. No Inter. No generic serif fonts. No pure black.
- No neon or outer-glow shadows. No oversaturated accents. No gradient text on large headers.
- No custom mouse cursors. No overlapping elements.
- No 3-column equal card rows. No centered hero.
- No generic names ("John Doe", "Acme"), no fake round numbers, no "Elevate / Seamless / Unleash / Next-Gen".
- No filler UI text: "Scroll to explore", scroll arrows, bouncing chevrons.
- No broken image links: only verified picsum.photos IDs.
