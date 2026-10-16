# Danishwer Design System

## Overview

Danishwer is a nonprofit providing education and healthcare support to individuals facing financial hardship. The design system reflects three values: **trust**, **hope**, and **clarity**. Every decision should communicate credibility and emotional warmth without being generic.

The visual identity draws from the logo's navy blue and forest green, referencing both the institutional gravitas of education and the life-affirming tone of healthcare. The design sits between editorial (Fraunces serif headlines) and precision UI (Hanken Grotesk for body and interface), borrowing spatial generosity from Apple and conversion clarity from Stripe.

---

## Color Tokens

### Brand

| Token | Hex | Usage |
|---|---|---|
| `--blue` | `#2563EB` | Primary actions, CTAs, links |
| `--navy` | `#1E408C` | Deep brand blue, gradient anchor |
| `--green` | `#1F7A47` | Success states, medical track, secondary brand |
| `--green-br` | `#2FA862` | Bright green accent, hover highlights |
| `--cyan` | `#06B6D4` | Supporting accent only (used sparingly) |

### Neutral

| Token | Hex | Usage |
|---|---|---|
| `--bg` | `#FAFBFC` | Page background |
| `--surface` | `#FFFFFF` | Cards, panels, modals |
| `--ink` | `#0E1A2B` | Primary text |
| `--muted` | `#52617A` | Secondary text, captions |
| `--line` | `#E7ECF3` | Borders, dividers, inactive states |

### Dark (footer/inverse)

| Token | Hex | Usage |
|---|---|---|
| `--dark-bg` | `#0B1626` | Footer and inverse section background |
| `--dark-text` | `#AEB9CC` | Footer body text |

### Gradients

```css
--grad: linear-gradient(115deg, #1E408C 0%, #2563EB 42%, #1F7A47 100%);
--grad-soft: linear-gradient(115deg, rgba(37,99,235,.10), rgba(31,122,71,.10));
```

The primary gradient runs from navy through bright blue to forest green. It encodes both brand colors in a single sweep. Use it on primary buttons, number highlights, icon badges, and key decorative elements. Do not use it as a full-page background; it belongs on focused elements.

---

## Typography

### Typefaces

| Role | Family | Source |
|---|---|---|
| Display / Headlines | Fraunces | Google Fonts (optical size 9–144) |
| UI / Body / Labels | Hanken Grotesk | Google Fonts |

**Why this pairing:** Fraunces is a characterful optical serif that carries emotional weight in large headlines without feeling like a traditional charity. Its variable optical size axis means it looks dramatically different at 60px versus 14px, which makes it ideal for hero headlines. Hanken Grotesk is a modern grotesque with distinctive letterforms and excellent screen rendering at small sizes; it avoids the overused "techy startup" feel of Inter or Space Grotesk.

### Type Scale

| Name | Size | Weight | Family | Usage |
|---|---|---|---|---|
| Display XL | clamp(2.6rem, 6vw, 4.4rem) | 600 | Fraunces | Hero headline |
| Display L | clamp(2rem, 4.4vw, 3.1rem) | 600 | Fraunces | Section headlines |
| Display M | 1.4–1.6rem | 600 | Fraunces | Card titles |
| Eyebrow | 0.78rem / 700 / UC / 0.14em | 700 | Hanken Grotesk | Section labels |
| Body L | 1.15–1.18rem | 400 | Hanken Grotesk | Hero subhead, lead copy |
| Body | 1rem | 400 | Hanken Grotesk | General body text |
| Body S | 0.92–0.95rem | 400 | Hanken Grotesk | Captions, meta |
| Label | 0.78–0.88rem | 600–700 | Hanken Grotesk | Tags, flow indicators |

### Rules

- Headlines: `line-height: 1.1`, `letter-spacing: -0.01em`
- Body: `line-height: 1.6`
- Gradient text (headlines): use `-webkit-background-clip: text` on the primary gradient only for display-level emphasis
- Never use Fraunces below 16px; it is a display face

---

## Spacing Scale

Based on an 8px base unit.

| Token | Value | Usage |
|---|---|---|
| xs | 8px | Inline gaps, icon padding |
| sm | 16px | Component internal spacing |
| md | 24px | Card padding (mobile) |
| lg | 34px | Card padding (desktop) |
| xl | 48px | Grid gaps |
| 2xl | 56px | Section head margin-bottom |
| 3xl | 90–110px | Section padding top/bottom |

Max content width: `1180px` with `24px` horizontal padding.

---

## Breakpoints

| Name | Width | Notes |
|---|---|---|
| Mobile S | 360px | Minimum supported viewport |
| Mobile | 480px | Portrait phones |
| Tablet | 768px | Landscape phones, small tablets |
| Tablet L | 980px | Full breakpoint: grids collapse |
| Desktop | 1180px | Standard desktop target |
| Wide | 1440px+ | Max-width kicks in, centered |

### Responsive Grid Behaviors

| Component | Desktop | Tablet (768px) | Mobile (480px) |
|---|---|---|---|
| Hero | 2-col split | 1-col stacked | 1-col, journey below |
| Impact stats | 4 cols | 2x2 | 2x2 |
| Timeline | 4 cols horizontal | 2x2 | 1-col vertical |
| Program cards | 3 cols | 1-col | 1-col |
| Story card | 2-col (photo + text) | 1-col | 1-col |
| Trust dashboard | 2-col | 1-col | 1-col |
| Get Involved | 3 cols | 1-col | 1-col |
| Donation | 2-col | 1-col | 1-col |
| Footer | 4 cols | 2-col | 1-col |
| Apply form steps | Centered 760px | Full width | Full width |

---

## Elevation / Shadows

| Level | Value | Usage |
|---|---|---|
| `--shadow-sm` | `0 1px 2px rgba(14,26,43,.06), 0 4px 12px rgba(14,26,43,.05)` | Cards at rest |
| `--shadow-md` | `0 8px 30px rgba(14,26,43,.08), 0 2px 6px rgba(14,26,43,.05)` | Cards on hover, modals |
| `--shadow-lg` | `0 24px 60px rgba(14,26,43,.12)` | Journey panel, hero elements |

All shadows use the `--ink` color at low opacity, never black. This keeps shadows warm and on-brand.

---

## Border Radius

| Token | Value | Usage |
|---|---|---|
| `--r` | `18px` | Standard cards |
| `--r-lg` | `26px` | Hero journey, story cards, large panels |
| `999px` | Pill | Buttons, nav pills, tags |
| `14–18px` | Medium | Form inputs, icon badges |

---

## Components

### Buttons

Three variants:

```
.btn-primary   gradient fill + white text + blue glow shadow
.btn-ghost     white fill + ink text + border line
.btn-call      green-tinted fill + green text (phone/contact CTAs)
```

All buttons: `border-radius: 999px`, `font-weight: 700`, `transition: transform + box-shadow`. On hover: `translateY(-2px)` + deeper shadow. Never use flat/borderless buttons for primary actions.

Minimum tap target: 44px height (met by `padding: 14px 26px`).

### Cards

Two main card types:

**Program/Feature card** (`--r-lg`, white surface, border `--line`, hover lifts `translateY(-8px)` + deeper shadow, gradient overlay fades in at opacity 1 on hover)

**Stats card** (centered, gradient number text, label in `--muted`)

### Nav

Glass pill nav: `backdrop-filter: blur(18px) saturate(160%)`, `rgba(255,255,255,.72)` background, centered in a `max-width: 1180px` container with floating pill appearance. Scrolled state adds heavier shadow. On mobile, collapses to hamburger that opens full-screen overlay.

### Form Inputs

```css
border: 1.5px solid var(--line);
border-radius: 12px;
padding: 13px 16px;
font-size: 1rem;
transition: border-color .2s, box-shadow .2s;

:focus {
  border-color: var(--blue);
  box-shadow: 0 0 0 3px rgba(37,99,235,.12);
  outline: none;
}
```

### Progress Wizard (Apply for Help)

7 numbered steps. Progress bar at top (animated width). Step dots below: inactive (gray), active (gradient fill + ring), completed (green check). Each step panel animated in with `fadeUp`. Navigation via Back/Next buttons; final step has Submit. Form validates required fields before advancing.

---

## Animation Principles

All animations respect `prefers-reduced-motion: reduce`. When that media query matches, all transitions are set to `none` and all animations to `none`.

| Animation | Trigger | Duration | Easing |
|---|---|---|---|
| Scroll reveal | IntersectionObserver (threshold 0.15) | 700ms | cubic-bezier(.2,.8,.2,1) |
| Number counter | IntersectionObserver (threshold 0.6) | 1600ms | Ease-out cubic |
| Blob float | Continuous CSS | 18s | ease-in-out, infinite |
| Flow arrows | Continuous CSS | 2.6s | linear, infinite |
| Bar fill (transparency) | IntersectionObserver | 1400ms | Ease |
| Timeline fill | IntersectionObserver | 1400ms | Ease |
| Card hover lift | Mouse | 300–350ms | cubic-bezier(.2,.8,.2,1) |
| Step advance | Button click | 400ms | Ease |
| Story carousel | Auto + click | 600ms | Ease |

Do not add more animations. The list above is the complete set. Additions must be justified against performance budget.

---

## Accessibility

- Color contrast: all body text on `--bg` exceeds WCAG AA (4.5:1 minimum). Gradient text used only for large display sizes where AA applies at 3:1.
- Focus indicators: all interactive elements have visible `:focus` outline (blue ring or elevated shadow).
- Touch targets: minimum 44x44px on all tappable elements.
- Keyboard navigation: all cards, form steps, and carousel controls are keyboard-operable.
- Screen readers: all images have descriptive `alt` text. `aria-label` on icon-only controls.
- Hamburger menu: `aria-label="Open menu"`.
- Animated elements: `prefers-reduced-motion` disables all motion.
- Semantic HTML: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`, `<h1>-<h3>` hierarchy maintained.

---

## Iconography

All icons are inline SVG using the Lucide icon style: 24x24 viewBox, `stroke-width: 2`, `stroke-linecap: round`, `stroke-linejoin: round`, fill none. Icon badges use a gradient background container (62x62 or 50x50 depending on context) with white stroke icons.

Do not mix icon styles. Lucide-only, inline SVG, no external icon library.

---

## Page Structure

Every page follows this structure:

```
<header> (glass nav, fixed)
<main>
  [page hero section]
  [content sections]
</main>
<footer> (dark footer)
```

Each `<section>` has class `.section` for standard `110px 0` padding, reducing at each breakpoint. Section heads use `.section-head` with max-width 680px, centered.

---

## Do Not Do List

- No purple (#7C3AED) as a primary or dominant color (it clashes with the logo's blue/green and is the single most overused "AI nonprofit" cliché).
- No particle.js or canvas-heavy particle systems (tanks performance on low-end Android phones, which is exactly who this site serves).
- No images from stock libraries with generic "charity" poses (diverse hands stacked, children with sad eyes, poverty aesthetics).
- No fake testimonial photos (AI-generated faces or random stock portraits).
- No auto-playing video in the hero.
- No pop-ups or interstitials that interrupt the donation or apply flow.
- No dark patterns in the donation flow (pre-checked recurring, hidden fees, misleading totals).
- No placeholder stats on the live site. Every number shown must be a real, verifiable figure.
