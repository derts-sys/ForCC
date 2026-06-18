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
