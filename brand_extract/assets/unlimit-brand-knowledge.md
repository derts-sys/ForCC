# Unlimit Brand Knowledge (for Claude Projects)

> Upload this single file to your Claude Project's **Project knowledge**. It bundles
> the full brand guide, design tokens (JSON) and the CSS implementation so Claude can
> style apps, dashboards, reports, presentations and files in Unlimit branding.
> Logos (SVG) and example backgrounds live alongside in the brand kit; attach them to
> a chat when you need the actual artwork embedded.

---

# Unlimit — Brand & Design Guide

Reusable styling reference for building **apps, dashboards, reports, presentations and files** under Unlimit branding.

**Sources:** extracted from *"Unlimit – Global Deck 2026"* + public unlimit.com brand language. Reflects the current brand (post **22.06.2025** rebrand).

---

## 1. Brand foundation
- **Name:** Unlimit (formerly Unlimint; rebranded May 2023, logo refreshed 22.06.2025)
- **Mission:** *Eliminate financial borders.*
- **Slogan:** *"borderless payments"*
- **Campaign line (deck):** *"Making global expansion easy."*
- **Tone of voice:** confident, clear, global, human, optimistic. Short declarative sentences. Lead with the customer outcome, not the plumbing.
- **Products to theme around:** Payment Processing (1000+ methods / APMs), White-Label **Card Issuing**, **Unlimit BaaS**, **Unlimit Crypto** (fiat on/off-ramp).
- **Regions:** Europe, UK, LatAm, APAC, Africa → world-map / connectivity motif.
- **Ambassador:** Simu Liu (borderless-payments campaign).

---

## 2. Logo
| Asset | File | Use |
|---|---|---|
| Wordmark (white) | `unlimit_wordmark_white.png` | On gradient/dark/photo backgrounds |
| Monogram "un" (white) | `unlimit_monogram_un.png` | Favicons, app icons, small spaces, slide corners |
| Wordmark (black) | `2025_unlimit-logo_black.png` *(in Drive)* | On light backgrounds |
| **Wordmark (vector)** | `unlimit_wordmark.svg` (+ `_black`/`_white`) | Scalable; `.svg` uses `currentColor` to inherit theme |
| **Monogram (vector)** | `unlimit_monogram.svg` (+ `_black`/`_white`) | Scalable monogram |

> The `.svg` files are **auto-traced from the PNGs** (clean for the wordmark; the monogram is from a 157 px source so edges are approximate). Good for web/UI at any size; for production print, still get the official vector from Marketing.

**Lockup with descriptor.** The official lockup pairs the wordmark with the
descriptor **"borderless payments"** set in two lines (Inter, smaller, same
colour) immediately to the **right** of the wordmark, baseline-aligned. Use the
lockup on covers, video-call backgrounds and formal touchpoints; the bare
wordmark is fine for tight UI. (See `social/` and `backgrounds/` for it in use;
request the exact lockup file/vector from Marketing.)

**Rules:** keep clear space ≥ the height of the "u" around the mark; never stretch, recolour outside brand colours, add shadows, or place the white logo on a busy light area without a scrim. Prefer the black wordmark on `#F5F5F9`/white; white wordmark on the gradient or dark.
> No vector (SVG/EPS) was embedded in the deck — request the official vector set from Marketing for print/large formats.

### Tagline system
- **Standing descriptor:** *"borderless payments"* (always with the logo lockup).
- **Campaign lockup:** *"Borderless [Variable]"* — the variable word(s) set in
  **lime** for emphasis, e.g. **"Borderless `Agentic Economy`"** (see the LinkedIn
  cover). Keep "Borderless" in white/ink, colour only the variable.

---

## 3. Colour
### Brand
| Role | Hex | Notes |
|---|---|---|
| Brand purple | `#6700FB` | Primary accent, links, primary buttons |
| Indigo | `#756AF3` | Secondary accent, gradient start |
| Lime | `#C9F73A` | Highlights, CTAs, quote marks |
| Lime bright | `#AFF41D` | Alt lime |
| Teal | `#24D8CC` | Energy/flow accent — social, ribbons, dark surfaces |
| Mint | `#9CF0D8` | Light teal tint |

### Neutrals
| Role | Hex |
|---|---|
| Ink (text) | `#1A1A1A` |
| Black | `#000000` |
| Grey (secondary) | `#7F7F7F` |
| Line / divider | `#E3E3EC` |
| Background | `#F5F5F9` |
| Cool panel | `#ECEEF5` |
| White | `#FFFFFF` |

### Semantic (UI states — derived to fit the palette)
`success #3CB37A` · `warning #F5A623` · `error #E5484D` · `info #756AF3`

### Gradients
- **Signature:** `linear-gradient(120deg, #756AF3, #4F93F0, #7BE36B, #6700FB)` — blue → green → purple (marketing / data surfaces).
- **Energy:** `linear-gradient(120deg, #02201F, #24D8CC, #C9F73A)` — dark teal → teal → lime (social / dark / high-impact).

### Dark theme
Half of Unlimit's real-world surfaces (video-call backgrounds, social) are
**dark**. On dark, **lime is the primary pop and teal the secondary** — purple
loses contrast, so avoid purple CTAs on dark.

| Role | Hex |
|---|---|
| Background | `#1A1A1A` |
| Dark teal panel | `#02201F` |
| Surface / card | `#26262A` |
| Border | `#3A3A40` |
| Text | `#FFFFFF` |
| Secondary text | `#A8A8B0` |

Apply via `<html data-theme="dark">` or `.unl-dark` in `unlimit-brand.css`.

### Accessibility
- Purple `#6700FB` on white ≈ 7:1 → safe for text and UI. **Do not** use purple as a CTA on dark (low contrast) — use lime or teal.
- **Lime `#C9F73A` is for accents/fills only — never lime text on white** (fails contrast). Put ink text on lime.
- Body text: ink `#1A1A1A` on `#F5F5F9`/white; white `#FFFFFF` on dark.

---

## 4. Typography
- **Display / headings:** **Nekst** (SemiBold default; Bold/Medium/Light/Regular).
- **Body / UI:** **Inter** (Light/Regular/SemiBold/Bold).
- **Fallbacks:** Montserrat → system-ui → Arial.
- Headings use tight tracking (−0.01 to −0.02em). Inter is free (Google Fonts); **Nekst is commercial — confirm licence before shipping.**

| Style | Size / line | Weight |
|---|---|---|
| Display | 48 / 1.05 | 600 |
| H1 | 36 / 1.1 | 600 |
| H2 | 28 / 1.15 | 600 |
| H3 | 22 / 1.2 | 600 |
| Body L | 18 / 1.5 | 400 |
| Body | 16 / 1.5 | 400 |
| Small | 14 / 1.45 | 400 |
| Caption | 12 / 1.4 | 400 |

---

## 5. Imagery & shape language
- **Two gradient families:** light/marketing = blue/green/purple glassy 3D shapes (`bg_cover_gradient.png`, `bg_green_orb.png`); dark/environmental = concrete & faceted 3D spaces with **lime/teal light strips** (`backgrounds/video-call/dark/…`).
- **Two modes, one pop:** light surfaces use grey neutrals with a single lime object as the hero; dark surfaces use near-black with lime + teal edges. Keep **one** pop colour dominant per composition.
- **Rounded** everything: pill buttons (`999px`), cards `16–24px`.
- World-map / region motif for global/coverage stories; teal **energy ribbons** for "borderless flow".
- Photography: real people, bright, optimistic; pair with lime quote marks.
- Generous whitespace on light `#F5F5F9`.

### Branded backgrounds & social (official)
- **Video-call backgrounds** — `backgrounds/video-call/light/` and `…/dark/` (1920×1080). Pick **light** if you're in a bright room, **dark** if dim (per the Meet setup manual). Carry the logo + "borderless payments" lockup top-left.
- **Social banners** — `social/` (LinkedIn cover = **1584×396**). Dark bg, energy ribbon, white wordmark, campaign word in lime. Editable starter: `Unlimit_LinkedIn_Banner_Template.png`.

---

## 6. Application recipes

### App / product UI
- Background `#F5F5F9`; cards white, radius 16px, shadow `0 8px 24px rgba(26,26,26,.08)`.
- Primary action = purple pill; secondary = ghost (purple outline); accent/CTA = lime.
- Nav/active state: purple; icons line-style, rounded.

### Dashboard
- Use the **chart palette in order:** `#6700FB → #C9F73A → #756AF3 → #3CB37A → #4F93F0 → #F5A623 → #9B5DE5 → #1A1A1A`.
- KPI numbers in Nekst SemiBold; status as tinted pills (`.tag-*`).
- One gradient hero/banner max per screen — keep data areas neutral for legibility.

### Report / document / file
- Cover: gradient or `bg_green_orb.png` + white wordmark + Nekst title.
- Body on white, ink text, grey captions; tables with grey Nekst headers + `#E3E3EC` rules.
- Footer: monogram + page number in grey. Accent figures/callouts in purple.

### Presentation
- 16:9, 1920×1080. Dark/gradient title slide; light content slides (`#F5F5F9`).
- One idea per slide, big Nekst headline, lime to highlight one keyword.
- Use the included PPTX template (`Unlimit_Brand_Template.pptx`) as a starting master.

---

## 7. Files in this kit
| File | What |
|---|---|
| `design-tokens.json` | All tokens (colour/type/radius/space/shadow/chart) for code |
| `unlimit-brand.css` | CSS variables + components (buttons, cards, tables, tags, chart vars) |
| `BRAND_GUIDE.md` | This guide |
| `unlimit_wordmark_white.png`, `unlimit_monogram_un.png` | Logos |
| `bg_cover_gradient.png`, `bg_green_orb.png` | Gradient backgrounds |
| `backgrounds/video-call/{light,dark}/…` | Official video-call backgrounds (1920×1080) |
| `social/linkedin_cover_*.png` | Official LinkedIn cover (1584×396) |
| `Unlimit_LinkedIn_Banner_Template.png` | Editable social banner template (1584×396) |
| `unlimit_wordmark.svg`, `unlimit_monogram.svg` (+ `_black`/`_white`) | Scalable vector logos |
| `brand-styleguide.html` | Interactive single-file living style guide (light/dark, click-to-copy) |
| `Unlimit_Brand_Book.pdf` | Visual brand book (incl. dark-theme page) |
| `Unlimit_Brand_Template.pptx` | Editable presentation template |

---

# Appendix A — design-tokens.json

```json
{
  "$meta": {
    "brand": "Unlimit",
    "source": "Unlimit – Global Deck 2026 (extracted) + unlimit.com brand language",
    "note": "Current brand, post 22.06.2025 rebrand. Slogan: 'borderless payments'. Mission: eliminate financial borders.",
    "updated": "2026-06-17"
  },
  "color": {
    "brand": {
      "purple":      { "value": "#6700FB", "desc": "Primary brand accent" },
      "indigo":      { "value": "#756AF3", "desc": "Secondary accent / gradient start" },
      "lime":        { "value": "#C9F73A", "desc": "Highlight / CTA accent" },
      "lime-bright": { "value": "#AFF41D", "desc": "Alt brighter lime" },
      "teal":        { "value": "#24D8CC", "desc": "Energy/flow accent (social, ribbons, dark expressions)" },
      "mint":        { "value": "#9CF0D8", "desc": "Light teal tint" }
    },
    "neutral": {
      "black":  { "value": "#000000" },
      "ink":    { "value": "#1A1A1A", "desc": "Default text" },
      "grey":   { "value": "#7F7F7F", "desc": "Secondary text / captions" },
      "line":   { "value": "#E3E3EC", "desc": "Borders / dividers (derived)" },
      "bg":     { "value": "#F5F5F9", "desc": "Default light background" },
      "bg-alt": { "value": "#ECEEF5", "desc": "Cool light panel" },
      "white":  { "value": "#FFFFFF" }
    },
    "semantic": {
      "success": { "value": "#3CB37A", "desc": "Derived – sits with lime/green family" },
      "warning": { "value": "#F5A623", "desc": "Derived" },
      "error":   { "value": "#E5484D", "desc": "Derived" },
      "info":    { "value": "#756AF3", "desc": "Reuses indigo" }
    },
    "chart": {
      "desc": "Ordered categorical palette for dashboards/reports",
      "values": ["#6700FB", "#C9F73A", "#756AF3", "#3CB37A", "#4F93F0", "#F5A623", "#9B5DE5", "#1A1A1A"]
    },
    "gradient": {
      "signature": "linear-gradient(120deg, #756AF3 0%, #4F93F0 30%, #7BE36B 60%, #6700FB 100%)",
      "subtle":    "linear-gradient(120deg, #F5F5F9 0%, #ECEEF5 100%)",
      "energy":    "linear-gradient(120deg, #02201F 0%, #24D8CC 60%, #C9F73A 100%)"
    },
    "dark": {
      "desc": "Dark theme – used across video-call backgrounds, social and high-impact surfaces",
      "bg":      { "value": "#1A1A1A", "desc": "Page background" },
      "bg-2":    { "value": "#02201F", "desc": "Dark teal panel" },
      "surface": { "value": "#26262A", "desc": "Cards / raised surfaces" },
      "line":    { "value": "#3A3A40", "desc": "Borders on dark" },
      "text":    { "value": "#FFFFFF", "desc": "Primary text on dark" },
      "text-2":  { "value": "#A8A8B0", "desc": "Secondary text on dark" },
      "accent":  { "value": "#C9F73A", "desc": "Primary pop on dark = lime" },
      "accent-2":{ "value": "#24D8CC", "desc": "Secondary pop on dark = teal" }
    }
  },
  "font": {
    "family": {
      "display": "Nekst, Montserrat, system-ui, sans-serif",
      "body":    "Inter, 'Helvetica Neue', Arial, sans-serif",
      "mono":    "'JetBrains Mono', ui-monospace, monospace"
    },
    "weight": { "light": 300, "regular": 400, "medium": 500, "semibold": 600, "bold": 700 },
    "scale": {
      "display": { "size": "48px", "line": "1.05", "weight": 600, "tracking": "-0.02em" },
      "h1":      { "size": "36px", "line": "1.1",  "weight": 600, "tracking": "-0.01em" },
      "h2":      { "size": "28px", "line": "1.15", "weight": 600 },
      "h3":      { "size": "22px", "line": "1.2",  "weight": 600 },
      "body-lg": { "size": "18px", "line": "1.5",  "weight": 400 },
      "body":    { "size": "16px", "line": "1.5",  "weight": 400 },
      "small":   { "size": "14px", "line": "1.45", "weight": 400 },
      "caption": { "size": "12px", "line": "1.4",  "weight": 400 }
    }
  },
  "radius": { "sm": "8px", "md": "16px", "lg": "24px", "pill": "999px" },
  "space":  { "xs": "4px", "sm": "8px", "md": "16px", "lg": "24px", "xl": "40px", "2xl": "64px" },
  "shadow": {
    "card": "0 8px 24px rgba(26,26,26,0.08)",
    "pop":  "0 12px 40px rgba(103,0,251,0.18)"
  },
  "slide": { "ratio": "16:9", "px": "1920x1080", "pt": "960x540" }
}
```

---

# Appendix B — unlimit-brand.css

```css
/* ============================================================
   UNLIMIT BRAND STYLESHEET
   Source: "Unlimit – Global Deck 2026" (extracted) + unlimit.com
   Current brand (post 22.06.2025 rebrand). Slogan: "borderless payments".
   Drop in and use the custom properties / utility classes below.
   ============================================================ */

:root {
  /* --- Brand colours --- */
  --unl-purple:      #6700FB;  /* primary accent / links / primary buttons */
  --unl-indigo:      #756AF3;  /* secondary accent / gradient start        */
  --unl-lime:        #C9F73A;  /* highlight / CTA accent / quote marks     */
  --unl-lime-bright: #AFF41D;
  --unl-teal:        #24D8CC;  /* energy/flow accent (social, dark, ribbons)*/
  --unl-mint:        #9CF0D8;  /* light teal tint                          */

  /* --- Neutrals --- */
  --unl-black:  #000000;
  --unl-ink:    #1A1A1A;   /* body text          */
  --unl-grey:   #7F7F7F;   /* secondary text     */
  --unl-line:   #E3E3EC;   /* borders / dividers */
  --unl-bg:     #F5F5F9;   /* page background    */
  --unl-bg-alt: #ECEEF5;   /* cool panel         */
  --unl-white:  #FFFFFF;

  /* --- Semantic (UI states) --- */
  --unl-success: #3CB37A;
  --unl-warning: #F5A623;
  --unl-error:   #E5484D;
  --unl-info:    #756AF3;

  /* --- Gradients --- */
  --unl-gradient:        linear-gradient(120deg, #756AF3 0%, #4F93F0 30%, #7BE36B 60%, #6700FB 100%);
  --unl-gradient-subtle: linear-gradient(120deg, #F5F5F9 0%, #ECEEF5 100%);
  --unl-gradient-energy: linear-gradient(120deg, #02201F 0%, #24D8CC 60%, #C9F73A 100%);

  /* --- Typography --- */
  --unl-font-display: "Nekst", "Montserrat", system-ui, sans-serif;
  --unl-font-body:    "Inter", "Helvetica Neue", Arial, sans-serif;
  --unl-font-mono:    "JetBrains Mono", ui-monospace, monospace;

  /* --- Radius / spacing / shadow --- */
  --unl-r-sm: 8px;  --unl-r-md: 16px;  --unl-r-lg: 24px;  --unl-r-pill: 999px;
  --unl-s-xs: 4px;  --unl-s-sm: 8px;   --unl-s-md: 16px;  --unl-s-lg: 24px;
  --unl-s-xl: 40px; --unl-s-2xl: 64px;
  --unl-shadow-card: 0 8px 24px rgba(26,26,26,0.08);
  --unl-shadow-pop:  0 12px 40px rgba(103,0,251,0.18);
}

/* --- Base --- */
body {
  background: var(--unl-bg);
  color: var(--unl-ink);
  font-family: var(--unl-font-body);
  font-size: 16px; line-height: 1.5; font-weight: 400;
}

h1, h2, h3, .display {
  font-family: var(--unl-font-display);
  font-weight: 600;
  color: var(--unl-ink);
  letter-spacing: -0.01em;
  margin: 0 0 .5em;
}
.display { font-size: 48px; line-height: 1.05; letter-spacing: -0.02em; }
h1 { font-size: 36px; line-height: 1.1; }
h2 { font-size: 28px; line-height: 1.15; }
h3 { font-size: 22px; line-height: 1.2; }
small, .caption { font-size: 14px; color: var(--unl-grey); }

a { color: var(--unl-purple); text-decoration: none; }
a:hover { text-decoration: underline; }

.accent      { color: var(--unl-purple); }
.accent-lime { color: var(--unl-lime); }

/* --- Buttons (pill, as in the deck) --- */
.btn { font-family: var(--unl-font-body); font-weight: 600; border: none;
       border-radius: var(--unl-r-pill); padding: 12px 24px; cursor: pointer; }
.btn-primary { background: var(--unl-purple); color: #fff; }
.btn-primary:hover { box-shadow: var(--unl-shadow-pop); }
.btn-accent  { background: var(--unl-lime); color: var(--unl-ink); }
.btn-ghost   { background: transparent; color: var(--unl-purple);
               box-shadow: inset 0 0 0 1.5px var(--unl-purple); }

/* --- Surfaces --- */
.card { background: #fff; border: 1px solid var(--unl-line);
        border-radius: var(--unl-r-lg); padding: var(--unl-s-lg);
        box-shadow: var(--unl-shadow-card); }
.hero { background: var(--unl-gradient); color: #fff;
        border-radius: var(--unl-r-lg); padding: var(--unl-s-2xl); }

/* --- Tables (reports) --- */
table { width: 100%; border-collapse: collapse; font-size: 14px; }
th { text-align: left; font-family: var(--unl-font-display); font-weight: 600;
     color: var(--unl-grey); border-bottom: 2px solid var(--unl-line);
     padding: 10px 12px; }
td { border-bottom: 1px solid var(--unl-line); padding: 10px 12px; }
tr:hover td { background: var(--unl-bg); }

/* --- Status pills (dashboards) --- */
.tag { display: inline-block; border-radius: var(--unl-r-pill);
       padding: 2px 10px; font-size: 12px; font-weight: 600; }
.tag-success { background: rgba(60,179,122,.15); color: var(--unl-success); }
.tag-warning { background: rgba(245,166,35,.15); color: #B97400; }
.tag-error   { background: rgba(229,72,77,.15);  color: var(--unl-error); }
.tag-info    { background: rgba(117,106,243,.15);color: var(--unl-info); }

/* --- Chart palette (use in order) --- */
:root {
  --unl-chart-1: #6700FB; --unl-chart-2: #C9F73A; --unl-chart-3: #756AF3;
  --unl-chart-4: #3CB37A; --unl-chart-5: #4F93F0; --unl-chart-6: #F5A623;
  --unl-chart-7: #9B5DE5; --unl-chart-8: #1A1A1A;
}

/* ============================================================
   DARK THEME
   Used across video-call backgrounds, social and high-impact
   surfaces. Apply via <html data-theme="dark"> or .unl-dark.
   On dark, lime is the primary pop and teal the secondary.
   ============================================================ */
[data-theme="dark"], .unl-dark {
  --unl-bg:     #1A1A1A;   /* page background          */
  --unl-bg-alt: #02201F;   /* dark teal panel          */
  --unl-ink:    #FFFFFF;   /* primary text             */
  --unl-grey:   #A8A8B0;   /* secondary text           */
  --unl-line:   #3A3A40;   /* borders                  */
  --unl-white:  #26262A;   /* "surface" token on dark  */
}
[data-theme="dark"] body, .unl-dark {
  background: var(--unl-bg); color: var(--unl-ink);
}
[data-theme="dark"] h1, [data-theme="dark"] h2, [data-theme="dark"] h3,
.unl-dark h1, .unl-dark h2, .unl-dark h3 { color: #FFFFFF; }
[data-theme="dark"] .card, .unl-dark .card {
  background: #26262A; border-color: #3A3A40; box-shadow: none;
}
/* On dark, prefer lime / teal CTAs (purple loses contrast) */
[data-theme="dark"] .btn-primary, .unl-dark .btn-primary {
  background: var(--unl-lime); color: var(--unl-ink);
}
[data-theme="dark"] .btn-accent, .unl-dark .btn-accent {
  background: var(--unl-teal); color: var(--unl-ink);
}
.hero-energy { background: var(--unl-gradient-energy); color: #fff;
               border-radius: var(--unl-r-lg); padding: var(--unl-s-2xl); }
```
