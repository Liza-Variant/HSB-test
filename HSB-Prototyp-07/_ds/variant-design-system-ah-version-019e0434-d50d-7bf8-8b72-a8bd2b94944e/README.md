# Variant Design System

Reusable design assets for **Variant** — a Norwegian consultancy of designers, developers and strategists. This system distills the official _Variant Identity – New Brand Starterpack_ Figma file into machine-usable tokens, components, and writing rules so design agents (and humans) can ship on-brand artefacts quickly.

> **Brand stance:** "Vi beviser det, vi sier det ikke" — _we prove it, we don't say it._ Concrete examples, named methods, real numbers, real customers. Then plain language. Then a yellow smiley shape if we have room.

---

## What this folder contains

```
.
├── README.md                ← you are here
├── SKILL.md                 ← Claude/Agent skill manifest
├── colors_and_type.css      ← all CSS variables + semantic type classes
├── assets/                  ← logos, the smiley, illustrations (SVG)
├── fonts/                   ← brand font files (see "Type" below)
├── preview/                 ← Design System tab cards
├── slides/                  ← 16:9 slide layouts (Britti Sans, paper-grey)
└── ui_kits/
    └── variant-website/     ← marketing-site UI kit
```

## Sources

| Source | Where |
|---|---|
| Figma — Variant Identity – New Brand Starterpack | mounted as `.fig` virtual filesystem (Cover / Logo / Typography / Color / Illustration / Shapes — 33 frames) |
| Variant tone-of-voice | provided as Norwegian copy excerpt; distilled in **Content Fundamentals** below |
| Variant website | https://www.variant.no (not fetched — included in case the reader has access) |

The reader may not have the Figma open. All design tokens, illustration motifs and component recreations referenced below have been copied into this project — you can build without it.

---

## Brand at a glance

- **Who:** Variant — Nordic tech & design consultancy (offices in Norway).
- **Voice:** Norwegian-first, friendly-direct, plain-spoken. Says _"vi"_ about itself, _"du/dere"_ about clients, never third-person.
- **Look:** Charcoal `#282828` ink on warm paper-grey `#F2F2F2`. One signature **Variant yellow** `#FFD42F`. A friendly smiley sun/blob mascot. Heavy 4px ink strokes for buttons. Geometric humanist sans (Britti Sans Variable).
- **Don't:** Stock-consultancy gradients. Drop shadows on cards. Emoji. Three-color call-to-action gradients. "Solutions that empower."

---

## Content fundamentals

Distilled from Variant's tone-of-voice document.

### Posture
Variant should read as **troverdig, engasjert og nysgjerrig** — credible, engaged, curious. Texts are **ærlige, åpne og transparente** — honest, open, transparent. That's the outer frame. The single sharpest rule inside it:

> **Vi beviser det, vi sier det ikke.** _We prove it, we don't say it._

Don't claim capability. Show it: name the framework, name the customer, give the number. The rule kills more bad copy than any other if you actually enforce it.

### Pronouns & person
- **Vi** about ourselves — always. Never "Variant" in third person, never "the team."
- **Du** or **dere** about the company you're talking to.
- Never **man**, never **bedriften**, never abstract "organisations."

### Sentence rules
- **Tydelig, kort, rett på sak.** Clear, short, to the point.
- If a sentence can be shortened, shorten it.
- No empty phrases ("levende strategier", "bærekraftige veivalg", "synergies").
- Metaphors that **illustrate** are fine. Metaphors that **replace** the point are not.
- Engagement words — **fantastisk**, **vi elsker**, **hurra** — are allowed but **dosert** (dosed). Sprinkle, don't pour.

### Casing
Sentence case for everything except the wordmark "Variant". Headlines lowercase except first word and proper nouns. Buttons sentence case ("Start here", "Les mer").

### Emoji
**Don't.** The smiley face is the brand mascot — drawing it as 🙂 cheapens it. Use the SVG `assets/smile-mouth.svg` over a yellow blob shape, or the avatar component.

### Worked example (from the brand doc)

| | |
|---|---|
| **Før** (29 words) | _Små og store organisasjonelle veivalg krever tydelig målbilder og levende strategier. Les mer om hvordan Variant kan hjelpe din organisasjon med å gjøre disse valgene færre, enklere og mer bærekraftige._ |
| **Etter** (13 words) | _Strategi handler om å lage gjennomførbare mål som gir motivasjon og resultater. — For å få til det har vi utviklet rammeverket Strategy x Summit._ |

The "etter" version is shorter, names the framework, and stops trying to sound impressive.

### English copy
Same rules, lowercase headlines, "we"/"you", short sentences. Variant publishes bilingually — when in doubt, write Norwegian first and translate down.

---

## Visual foundations

### Colour
- **One brand colour does the heavy lifting:** `--variant-yellow` `#FFD42F`. Used for the smiley blob, the V-mark fill, illustration accents, occasional tag/highlight. **Never as page background** behind body text — yellow is a shape, not a sheet.
- **Charcoal `#282828`** is the working ink — text, button strokes, the V wordmark, eyes/mouth on the smiley. Pure black `#000` is reserved for the printed wordmark.
- **Paper grey `#F2F2F2`** is the canonical canvas (slide background, large hero blocks). White `#FFFFFF` for cards and product surfaces.
- **A 9-hue × 11-shade spectrum** (Coral / Purple / Perrywinkle / Blue / Teal / Green / Yellow / Orange / Grey, shades 25 → 900) exists for editorial / illustration / data viz — not for chrome. See `colors_and_type.css`.
- Pair rule: **dark on light or light on dark, never colour on colour at low contrast.** The Figma Color Combo Tests file passes pairs at AA+; high-saturation 500/600 always pair with 25/50 of the same hue or with ink/white.

### Type
- **Britti Sans Variable** (Klim Type Foundry, commercial). Geometric humanist sans with friendly aperture and slightly rounded terminals. Variable axis: 200–900.
- **Brand fonts shipped** in `fonts/` — `BrittiSans-Regular.otf`, `BrittiSans-RegularItalic.otf`, `BrittiSans-Semibold.otf`, `BrittiSans-SemiboldItalic.otf`. Semibold is mapped to weight `600–900` so any `font-weight:700/800` calls render in Semibold (the heaviest cut on hand). **Hanken Grotesk** stays as a graceful fallback while OTFs load.
- **Inter Regular** is used in the source file at 48px in one limited place; not part of the system.
- Hierarchy is built with **size + weight**, not colour. Hero/Display use Medium (500); body in Regular (400); button labels Bold (700).
- Negative tracking on display (-0.02em). Body sits at 0. Captions get +0.02em and uppercase.

### Backgrounds
- **No gradients on chrome.** Gradients only show up inside illustrations as colour-spectrum studies.
- **No grain, no noise, no photo backgrounds.** Variant's surface is flat, paper-grey or white.
- **Full-bleed yellow blob shapes** are used as background décor on hero areas — rotated rounded-rectangles with eyes & smile. See `assets/yellow-blob*.svg`.

### Borders & strokes
- Buttons: **4px ink stroke**, no fill (or yellow fill on dark surfaces). Pill radius (~40px+).
- Card outlines: 1px `--grey-200` or no outline at all (rely on background contrast).
- Illustration outlines: heavy 7px ink strokes — matches the smiley face geometry.
- A **purple dashed `1px dashed --purple-400`** outline appears in the Figma file to mark _component instances_ — that's a Figma annotation, not a brand element. Don't ship dashed purple in the wild.

### Shadows
- Effectively **none**. Variant uses contrast and the 4px ink stroke for separation.
- The single shadow in the source file (`rgba(0,0,0,0.4)` × 1×) is incidental.
- For menus / overlays we provide subtle `--shadow-sm/md/lg` tokens — use sparingly.

### Radii
- **Pill** (`--radius-pill`) for buttons and small badges.
- **24–40px** rounded rectangles for hero cards.
- **Large radii (3000+)** for the smiley blob — read as an organic egg, not a circle.
- Avoid 4–8px corner radii on big surfaces; they look webby and fight the brand.

### Imagery
- Brand illustration is **flat vector, two colours** (yellow + ink). Drawn shapes: rounded rectangles, ellipses, the V-mark, rectangles in stacked drift. No photography in the brand starter — when photos appear in the wild they sit inside a yellow blob frame.
- Mood: warm, hand-arranged but geometric. Slight rotation on individual shapes (3–10°) to feel human-placed.
- The smiley face: two black dots + a 7px curved stroke. Always inside a yellow blob/pill.

### Animation
- The brand pack ships static — no motion guide is provided.
- House recommendation (matches the brand's friendly-but-grown-up posture):
  - **Easing:** `cubic-bezier(0.2, 0.8, 0.2, 1)` for entrances, `cubic-bezier(0.4, 0, 0.2, 1)` for state changes.
  - **Duration:** 180ms (state), 240ms (small UI), 360ms (page-level), 600ms+ only for hero illustrations.
  - **Bounce sparingly** — the smiley wobble is the brand's only "personality" motion.
  - **Fade > slide.** Don't slide content unless it spatially comes from somewhere.

### Hover, focus, press
- **Hover:** opacity → 0.9, or background darken by one shade (`yellow-400 → yellow-500`). Cursor `pointer`.
- **Focus:** 2px outline `--variant-ink` offset 2px. Always visible. Never remove.
- **Press:** scale 0.97, no colour change. ~80ms.
- **Disabled:** opacity 0.4, no cursor.

### Layout
- **Slide grid:** 1920×1080, 120px gutter, content max-width ~1680.
- **Web grid:** 12-column, 80px gutter on desktop, generous vertical rhythm (96/120 px section padding).
- Fixed elements: the **V-mark** sits top-left at 60×60 (slide) or 48×48 (web). The "Variant Logo Badge" pill sits bottom-right on chapter slides.
- **Big white space.** The brand starter pack uses a lot of empty surface; don't fill it.

### Transparency & blur
- **No backdrop blur.** No semi-transparent surfaces in the brand pack.
- Transparency only inside SVG illustrations for layered shapes.

---

## Iconography

The Variant Starterpack does **not** ship a system icon set. The brand library is illustration-led — what looks like icons (the V-mark, the smiley) are brand marks, not UI affordances.

For UI work in this project we use **[Lucide](https://lucide.dev/)** via CDN as the substituted icon set:
- 24px / 1.75px stroke (matches Britti Sans cap-height & feels companionable to Hanken Grotesk).
- Stroke colour `--fg`. Never multi-colour.
- Lucide is rounded-cap, geometric, slightly-friendly — closest match to Britti Sans's character.

```html
<script src="https://unpkg.com/lucide@latest"></script>
<i data-lucide="arrow-right"></i>
<script>lucide.createIcons();</script>
```

⚠️ **Substitution flagged for the user.** If Variant has internal icon SVGs in product code, drop them into `assets/icons/` and update this section.

### Brand marks (not icons — don't reuse as UI)
- `assets/variant-wordmark.svg` — the "Variant" word, ink.
- `assets/variant-logo-pill.svg` — wordmark inside the ellipse (filled or outlined badge).
- `assets/v-mark-square.svg` — the V inside a rotated yellow square (small avatar mark).
- `assets/yellow-blob.svg`, `yellow-blob-2.svg`, `yellow-blob-3.svg`, `yellow-blob-large.svg`, `yellow-blob-large-2.svg`, `yellow-pill.svg` — the smiley sun shape family. Combine with `smile-mouth.svg` and two ink dots.
- `assets/illustration-refill.svg`, `vector-fagpost-1.svg`, `vector-fagpost-2.svg`, `scribble-union.svg` — editorial illustration fragments.

### Emoji
**No.** Use SVG. Especially: don't use 🙂 in copy when the brand has a real face.

### Unicode glyphs
The arrow `→` is used as a UI char in slide breadcrumbs (`Innholdsside` template uses `→` between section titles). That's the only meaningful unicode-as-icon usage in the source.

---

## Index

| File | What it gives you |
|---|---|
| `colors_and_type.css` | All CSS variables (colour spectrum, ink/paper, semantic tokens, radii, spacing, type sizes) and `.t-hero/.t-display/.t-h1…/.t-body/.t-caption` semantic classes. **Import this first.** |
| `assets/` | Brand SVGs — logos, smiley shapes, editorial illustration fragments. |
| `preview/` | Cards rendered in the Design System tab — palette, type specimens, component states. |
| `slides/` | Reference slide layouts (cover / chapter / content / quote / two-column). 1920×1080. |
| `ui_kits/variant-website/` | Marketing-site UI kit: header, hero, case-card, footer, CTA pill. |
| `SKILL.md` | Skill manifest so this folder works as a portable Claude/Agent skill. |

---

## Caveats

- **Britti Sans** Regular + Semibold (with italics) are now in `fonts/`. A true Bold/Black cut is not on hand, so the @font-face block maps Semibold across `600–900`; if Variant has a Bold OTF, drop it in and add a matching `@font-face`.
- **Color spectrum 25–900 values** are derived from the visual spectrum + the explicit overrides found in the Figma pseudocode (`#FFD42F`, `#FD7768`, `#560C4A`, etc). Edge shades (25, 50) are interpolated; if Variant has authoritative tokens elsewhere, swap them in.
- **Lucide** stands in for an icon system because the Figma pack doesn't ship one. If Variant's product code has SVGs, drop them in and update ICONOGRAPHY.
- **No motion guide** existed in the source — the Animation section is a house recommendation matching the brand's quiet personality.
