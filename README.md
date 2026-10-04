<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B0B0B,100:FF2A2A&height=210&section=header&text=danix29.github.io&fontSize=50&fontColor=EAEAEA&fontAlignY=38&desc=Industrial%20brutalism%20%C2%B7%20one%20HTML%20file%20%C2%B7%20zero%20dependencies&descAlignY=60&descColor=EAEAEA&animation=fadeIn" width="100%"/>

<div align="center">

[![Live](https://img.shields.io/badge/LIVE-danix29.github.io-FF2A2A?style=for-the-badge&labelColor=161616&logo=googlechrome&logoColor=white)](https://danix29.github.io)
[![Skins](https://img.shields.io/badge/9_DESIGN_SKILLS-%2Fskins-161616?style=for-the-badge&labelColor=FF2A2A)](https://danix29.github.io/skins/)
[![Deploy](https://github.com/Danix29/Danix29.github.io/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/Danix29/Danix29.github.io/actions/workflows/pages/pages-build-deployment)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/Vanilla_JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Frameworks](https://img.shields.io/badge/frameworks-0-161616?style=flat-square)
![Build](https://img.shields.io/badge/build_step-none-161616?style=flat-square)
![Files](https://img.shields.io/badge/site-1_HTML_%2B_1_SVG-161616?style=flat-square)
![i18n](https://img.shields.io/badge/i18n-EN_%7C_ES-FF2A2A?style=flat-square)
![a11y](https://img.shields.io/badge/reduced--motion-respected-FF2A2A?style=flat-square)

<a href="https://danix29.github.io">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/hero-dark.png"/>
    <source media="(prefers-color-scheme: light)" srcset="assets/hero-light.png"/>
    <img src="assets/hero-dark.png" alt="danix29.github.io hero: DANIEL DEL NOGAL BUCHANAN in a brutalist frame" width="100%"/>
  </picture>
</a>

<sub>The screenshot follows your GitHub theme: dark substrate in dark mode, Swiss-print paper in light mode. The site has the same toggle.</sub>

</div>

---

## ⏻ Boot sequence

<div align="center">

<img src="assets/boot.gif" alt="Boot intro: terminal log, counter from 000 to 100 percent, slatted exit into the hero" width="88%"/>

</div>

Every visit opens with a ~2.5 s boot: a terminal log, a stepped counter from `000` to `100 %`, a segmented load bar and six slats that retract to reveal the hero. Skip it with a click, <kbd>Esc</kbd>, <kbd>Enter</kbd> or <kbd>Space</kbd>. It never plays under `prefers-reduced-motion`, and a CSS failsafe hides it after 8 s if JavaScript dies.

---

## ▦ Design system

<table>
<tr>
<td width="50%" valign="top">

**Palette** · one accent, no gradients

| | Token | Role |
|---|---|---|
| ![](https://img.shields.io/badge/%20%20%20-0B0B0B?style=for-the-badge) | `#0B0B0B` | Carbon substrate |
| ![](https://img.shields.io/badge/%20%20%20-EAEAEA?style=for-the-badge) | `#EAEAEA` | Phosphor ink |
| ![](https://img.shields.io/badge/%20%20%20-FF2A2A?style=for-the-badge) | `#FF2A2A` | Aviation red, the only accent |
| ![](https://img.shields.io/badge/%20%20%20-4AF626?style=for-the-badge) | `#4AF626` | Terminal green, exactly one status light |
| ![](https://img.shields.io/badge/%20%20%20-EAE8E3?style=for-the-badge) | `#EAE8E3` | Light theme: unbleached paper |

</td>
<td width="50%" valign="top">

**Type** · two families, extreme contrast

![Archivo](https://img.shields.io/badge/Archivo_900-HEADLINES-EAEAEA?style=for-the-badge&labelColor=0B0B0B)
![JetBrains Mono](https://img.shields.io/badge/JetBrains_Mono-METADATA-FF2A2A?style=for-the-badge&labelColor=0B0B0B)

**Rules**

- `border-radius: 0` everywhere
- 2 px compartments drawn with the `gap` + ink-parent trick
- Motion runs on `steps()`, like machinery
- Blueprint grid, CRT scanlines and SVG grain on fixed layers
- Display type sized from its **container** (`cqi`), so it never overflows, even with a larger browser font

</td>
</tr>
</table>

---

## ▤ Sections

<table>
<tr>
<td width="50%"><img src="assets/section-stack.png" alt="Stack: skill radar and segmented meters"/><br><sub><b>02 · Stack</b> · canvas radar + segmented meters that fill on first view</sub></td>
<td width="50%"><img src="assets/section-projects.png" alt="Projects: gapless grid with filters"/><br><sub><b>03 · Projects</b> · gapless grid, filters, cards invert on hover</sub></td>
</tr>
<tr>
<td width="50%"><img src="assets/section-experience.png" alt="Experience: log-style entries"/><br><sub><b>05 · Experience</b> · log entries <code>JOB-01 // STATUS: ACTIVE</code></sub></td>
<td width="50%"><img src="assets/section-education.png" alt="Education: currently banner and enrolment"/><br><sub><b>06 · Education</b> · 2026–27 enrolment, Fortinet NSE 1–3, history</sub></td>
</tr>
<tr>
<td width="50%"><img src="assets/section-contact.png" alt="Contact: oversized headline and link table"/><br><sub><b>07 · Contact</b> · oversized CTA + link table</sub></td>
<td width="50%" align="center"><img src="assets/mobile.png" alt="Mobile view of the hero" width="58%"/><br><sub><b>Mobile</b> · single column below 768 px, no horizontal scroll</sub></td>
</tr>
</table>

Also on the page: **01 · About** (bio, stats, language meters), **04 · Interests**, a scroll-scrubbed manifesto and two marquees.

---

## ⌨ Interactions

| | | | |
|:---:|---|:---:|---|
| ⏻ | Boot intro, skippable | ◐ | Dark / Swiss-print light theme, remembered |
| 🌐 | EN / ES switch, remembered | ▦ | Shutter reveals in 6 mechanical steps |
| ▸ | Typed terminal after the boot | ◉ | Radar + meters animate on first view |
| ⧉ | Project filters that keep the grid gapless | ▤ | Word-by-word scroll-scrubbed statement |
| <kbd>?</kbd> | Shortcuts panel | <kbd>g</kbd> + letter | Jump to a section |
| <kbd>t</kbd> | Toggle theme | <kbd>l</kbd> | Toggle language |

<sub>And a Konami code. You know the one.</sub>

---

## ⧉ Nine design skills, one portfolio

<div align="center">

<a href="https://danix29.github.io/skins/"><img src="assets/skins-mosaic.jpg" alt="The portfolio rendered with nine design skills" width="100%"/></a>

</div>

The same content rendered nine times, each page following the rules of a different design skill: **taste-skill**, **taste-skill-v1**, **gpt-tasteskill** (real GSAP ScrollTrigger), **soft-skill**, **minimalist-skill**, **brutalist-skill** (this site), **stitch-skill** (+ its [`DESIGN.md`](skins/stitch-skill-DESIGN.md)), **apple-design** (real spring physics) and **emil-design-eng**. They carry no analytics and are `noindex`. → [danix29.github.io/skins](https://danix29.github.io/skins/)

---

<details>
<summary><b>⚙ Under the hood</b></summary>
<br>

| Layer | Choice | Why |
|---|---|---|
| HTML | Single `index.html` | Zero build step, zero dependencies |
| CSS | Inline `<style>`, tokens in `:root` | Self-contained; the light theme only swaps tokens |
| JS | One IIFE in an inline `<script>` | No framework; one rAF-throttled passive scroll listener |
| Fonts | Google Fonts: Archivo + JetBrains Mono | Preconnect, `display=swap` |
| Hosting | GitHub Pages | Deploys on every push to `main` |

```
Danix29.github.io/
├── index.html        ← the whole site
├── favicon.svg       ← black/white "DN" plate with a red band
├── skins/            ← nine design-skill variants + gallery + DESIGN.md
├── assets/           ← screenshots used in this README
└── README.md
```

**Analytics** · [GoatCounter](https://www.goatcounter.com) (no cookies, GDPR-friendly) and [Microsoft Clarity](https://clarity.microsoft.com) (heatmaps, session recordings), both async.

**SEO** · `description`, Open Graph and Twitter Card tags; OG image generated with [capsule-render](https://github.com/kyechan99/capsule-render).

**Local**

```bash
python -m http.server 8080   # then open http://localhost:8080
```

</details>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:FF2A2A,100:0B0B0B&height=110&section=footer" width="100%"/>

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-danieldnb-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/danieldnb/)
[![Profile](https://img.shields.io/badge/GitHub-Danix29-161616?style=flat-square&logo=github&logoColor=white)](https://github.com/Danix29)
[![Resume](https://img.shields.io/badge/Resume-Harvard_EN%2FES-FF2A2A?style=flat-square&logo=readthedocs&logoColor=white)](https://github.com/Danix29/Resume)

<sub>Daniel Del Nogal Buchanan · Computer Engineering · Universidad de Alcalá</sub>

</div>
