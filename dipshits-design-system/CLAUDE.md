# DIPSHITS — Brand & Design System

> *Crunch loud. Dip louder.* 🌶️

A loud, joyful, 1980s pop-art brand of nachos and dips. This file is the complete brief for any AI coding agent building Dipshits surfaces (website, slide decks, applications). Pair it with `tokens.css` for drop-in tokens and utility classes.

## 30-second brand brief

| | |
|---|---|
| **Vibe** | 1980s pop-art on a bag of chips. Loud, joyful, slightly chaotic. Mexican folk-art palettes filtered through Memphis-Group geometry. |
| **Mission** | Spread joy. Make snacking ridiculous. Take the boring out of dip. |
| **Personality** | The friend who turns up with five salsas, gives unsolicited compliments, and means every one. Confident, warm, a tiny bit reckless. |
| **Audience** | 18–35 snackers, party people, the chronically online, anyone who treats dip as a personality trait. |

## The 10 rules (cheat sheet)

1. Background is **cream tortilla** (`#FFF6E5`). Never white.
2. Every layout uses **at least 3 saturated colors**. Two-color layouts feel half-finished.
3. **Bagel Fat One** for huge ALL-CAPS display. **Caveat Brush** for handwritten "say hi to" overlines.
4. Headlines and stickers **tilt between −4° and +6°**. Nothing is perfectly orthogonal.
5. Shadows are **flat hard offsets** (`6px 6px 0 var(--ink)`). Never blurry on UI.
6. Borders are **chunky** (3–4px solid `--ink`). Cards look punched out of a cereal box.
7. Buttons are **pills** with hard shadow. Hover lifts + jiggles. Press collapses the shadow.
8. Icons are **Phosphor Bold** in a brand color. Never gray.
9. Voice is **short, percussive, kind, irreverent**. Use "you" liberally. No corporate fog.
10. Emoji exist but are seasoning, not the meal. House set: 🌶️ 🥑 🌮 🌽 🔥 🎉 😎 ✨

## Color

Eight saturated primaries plus warm neutrals. All CSS custom properties live in `tokens.css`.

| Token | Hex | When to reach for it |
|---|---|---|
| `--hot-pink` | `#FF2D8F` | Hero accents, links, primary buttons |
| `--electric-yellow` | `#FFD60A` | Stickers, callouts, sunny moods |
| `--lime` | `#1FBF5C` | Success, fresh, herbaceous |
| `--royal-blue` | `#2D52E0` | Secondary CTAs, info, cool moments |
| `--salsa-red` | `#E8222B` | Heat, danger, exclamation |
| `--grape` | `#6B2BB8` | Depth, contrast, late-night |
| `--mango` | `#FF6B1F` | Warmth, warning, sweetness |
| `--mint` | `#14C4B9` | Cool counterpoint, accents |
| `--tortilla` | `#FFF6E5` | **Default page bg** |
| `--ink` | `#1A1313` | Body text, borders, shadows (never `#000`) |

**Rules:**

- Default page bg is `--tortilla`. Use saturated colors for section blocks.
- Pair any two saturated primaries freely. Mexican-textile rule: stack more colors when in doubt.
- Text on saturated bg: `--tortilla` for cream-on-color, `--ink` for ink-on-yellow/lime/mint (light hues).
- Status colors map to brand: `--success: --lime`, `--warning: --mango`, `--danger: --salsa-red`, `--info: --royal-blue`.

## Type

Four families, all free Google Fonts (already imported in `tokens.css`).

| Family | CSS var | Use | Notes |
|---|---|---|---|
| Bagel Fat One | `--font-display` | Display headlines | ALL CAPS, single weight, chunky retro |
| Caveat Brush | `--font-script` | "Say hi to" overlines, casual asides | Rotate −3° for handwritten feel |
| Space Grotesk | `--font-subhead` | Sub-heads, UI labels, eyebrows | 700 for emphasis |
| DM Sans | `--font-body` | Body, paragraphs, captions | Sentence case |

**Scale**: ready-made classes `.ds-mega`, `.ds-display`, `.ds-h1`–`.ds-h4`, `.ds-body`, `.ds-body-lg`, `.ds-script`, `.ds-eyebrow`, `.ds-small`, `.ds-caption`, `.ds-mono`.

**Standard pattern**: script eyebrow → giant display headline → body paragraph.

```html
<span class="ds-script">say hi to</span>
<h1 class="ds-mega">CRUNCH LOUD.<br/>DIP LOUDER.</h1>
<p class="ds-body-lg">Wildly fresh dips. Ridiculously crunchy chips.</p>
```

## Voice and copy

Write like the loudest, kindest friend at the party.

- **Short, percussive sentences.** Crunch. Dip. Smile. Repeat.
- **Real verbs, not corporate fog.** "Made of mango" beats "Crafted with artisanal mango."
- **"You" for the snacker, "we" for the brand.** Never third-person product-speak.
- **One exclamation point per sentence, max.** Confident, not yelling.
- **Em-dashes — yes, lots — they keep things conversational.** (Brand voice exception; in product/UI prose, keep them measured.)
- **The joke is never at anyone's expense.** Irreverent but kind. The target of the wink is dip itself, the situation, or us.

**Casing:** Display = ALL CAPS. Sub-heads & CTAs = Title Case or ALL CAPS. Body = sentence case. Product names = Title Case.

### Yes
- *Crunch loud. Dip louder.*
- *Say hi to your new favorite dip.*
- *Made of mango. Powered by maximum chill.*
- *Five dips. Zero regrets.*

### No
- ~~Our premium artisanal salsas are crafted with care.~~ (corporate fog)
- ~~CRAZY GOOD!!! 🌶️🌶️🔥🔥😋😋~~ (yelling, emoji spam)
- ~~Why settle for ordinary chips?~~ (no trash-talk)

## Layout and composition

- **Asymmetry over symmetry.** Stagger sections left/right. No center-everything pages.
- **Big margins, big type.** Desktop page padding 64px (`--s-8`); headlines clamp 80–160px.
- **Tilt key elements.** Stickers, headlines, packaging shots rotate −4° to +6°.
- **Stickers, ribbons, starbursts** are first-class composition pieces, not just containers.
- **Max width** `--maxw: 1240px`. Gutter `--gutter: 32px`.

## Components (drop-in patterns)

`tokens.css` ships utility classes for the four most-used components. Inline-style snippets below are for React/JSX use.

### Button — pill with chunky shadow

HTML: `<button class="ds-button ds-button--primary">Shop dips →</button>`

JSX:
```jsx
<button style={{
  fontFamily: "var(--font-display)",
  textTransform: "uppercase",
  letterSpacing: "0.02em",
  background: "var(--hot-pink)",
  color: "var(--tortilla)",
  border: "3px solid var(--ink)",
  borderRadius: 999,
  padding: "12px 24px",
  fontSize: 18,
  boxShadow: "5px 5px 0 var(--ink)",
  cursor: "pointer",
  transition: "transform 140ms var(--ease-bounce), box-shadow 140ms",
}}
  onMouseDown={e => { e.currentTarget.style.transform = "translate(3px,3px)"; e.currentTarget.style.boxShadow = "0 0 0 var(--ink)"; }}
  onMouseUp={e => { e.currentTarget.style.transform = ""; e.currentTarget.style.boxShadow = ""; }}>
  Shop dips →
</button>
```

Variants: `--primary` (hot-pink), `--secondary` (royal-blue), `--yellow` (electric-yellow on ink), `--ghost` (tortilla on ink).

### Card — "punched out of a cereal box"

HTML: `<div class="ds-card">…</div>`

```jsx
<div style={{
  background: "var(--tortilla)",
  border: "3px solid var(--ink)",
  borderRadius: 20,
  boxShadow: "6px 6px 0 var(--hot-pink)",
  padding: "var(--s-6)",
}}>…</div>
```

Vary the shadow color (`--hot-pink`, `--royal-blue`, `--electric-yellow`) to swap mood without changing the layout.

### Sticker — round, tilted, chunky

HTML: `<div class="ds-sticker" style="--bg: var(--salsa-red); --fg: var(--tortilla)">NEW<br/>FLAVOR!</div>`

```jsx
<div style={{
  width: 96, height: 96, borderRadius: 999,
  border: "3px solid var(--ink)",
  background: "var(--salsa-red)", color: "var(--tortilla)",
  display: "grid", placeItems: "center",
  fontFamily: "var(--font-display)", fontSize: 16, textTransform: "uppercase",
  textAlign: "center", lineHeight: 0.95,
  boxShadow: "4px 4px 0 var(--ink)",
  transform: "rotate(-8deg)",
}}>NEW<br/>FLAVOR!</div>
```

### Diagonal stripes — hero / section background

```css
background: repeating-linear-gradient(
  -65deg,
  var(--hot-pink) 0 56px,
  var(--mint) 56px 112px
);
```

### Serape band — footer / divider

```css
background: repeating-linear-gradient(
  90deg,
  var(--mango) 0 40px, var(--electric-yellow) 40px 80px,
  var(--lime) 80px 120px, var(--royal-blue) 120px 160px,
  var(--hot-pink) 160px 200px, var(--grape) 200px 240px
);
height: 22px;
border-top: 3px solid var(--ink);
```

### Patterns

`assets/stripe-pattern.svg` and `assets/halftone-dots.svg` work as tiled `background-image` for texture fills.

## Iconography

Phosphor Bold via CDN. Icons inherit `currentColor` and take a brand color.

```html
<script src="https://unpkg.com/@phosphor-icons/web@2.1.1"></script>
<i class="ph-bold ph-fire" style="color: var(--salsa-red); font-size: 24px"></i>
```

Sizes: 16, 20, 24, 32, 48. Never gray.

## Assets (in `assets/`)

| File | Use |
|---|---|
| `dipshits-wordmark.svg` | Main wordmark |
| `smiley-shades.svg` | Hero mascot — heart-sunglasses chip smiley |
| `stripe-pattern.svg` | Diagonal stripe tile |
| `halftone-dots.svg` | Halftone dot tile |
| `starburst.svg` | Sale / explosion callout |

All SVGs follow brand vocabulary: chunky shapes, thick black outlines or no outline at all. Recolor freely with `fill` or `currentColor`.

## Motion

- **Fast, bouncy, mischievous.** Durations 140–280ms.
- **Default easing** `--ease-bounce` (`cubic-bezier(0.34, 1.56, 0.64, 1)`) with overshoot.
- **Hover**: lift + 1–2° rotate. Shadow shifts. Never a fade-to-darker.
- **Press**: shadow collapses to `0 0 0`; element nudges by the shadow offset (feels like the button got slammed onto the table).
- **Idle wobble** allowed on hero stickers and mascots. Respect `prefers-reduced-motion`: keep transitions, drop rotation.

## Implementation

Drop `tokens.css` into your project. Load Phosphor for icons.

```html
<link rel="stylesheet" href="tokens.css"/>
<script src="https://unpkg.com/@phosphor-icons/web@2.1.1"></script>
```

For **React**: import `tokens.css` once at the root, then style with `var(--token)` inline or via styled-components.

For **slide decks**: 1280×720 canvas, tortilla background, headline ~140px Bagel Fat One, content via `.ds-h2/h3`. Tilt one or two key elements per slide.

For **applications**: relax the tilt and chunky shadows in dense product UI, but keep the type stack, palette, and pill buttons. Cards still get 3px ink border and `--r-lg` radius.

## Hard nos

- White backgrounds (use `--tortilla`).
- Pure `#000` (use `--ink`).
- Center-everything page layouts.
- Two-color-only layouts.
- Blurred drop shadows on UI elements.
- Gray icons.
- Hedging language ("kind of", "perhaps", "we believe").
- Emoji spam.
- Gradients as primary surfaces (chrome on display type is the only allowed gradient).
- Timid 1–2px borders on cards.

---

**File map**

- `tokens.css` — all design tokens (colors, type, spacing, radii, shadows, motion) plus utility classes for type and core components.
- `assets/` — marks, mascot, patterns.
- `CLAUDE.md` — this brief: brand rules, voice, code snippets.
