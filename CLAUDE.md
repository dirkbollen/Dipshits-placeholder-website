# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development

No build step. Open files directly in a browser:

```bash
open index.html
open dipshits-design-system/example.html
```

## Project structure

| Path | Purpose |
|---|---|
| `index.html` | Placeholder landing page ("Please don't contact us") |
| `dipshits-design-system/tokens.css` | All design tokens + utility classes — the single source of truth for color, type, spacing, radii, shadows, motion |
| `dipshits-design-system/example.html` | Live reference for every token and component |
| `dipshits-design-system/assets/` | SVGs: wordmark, mascot (smiley-shades), starburst, stripe-pattern, halftone-dots |
| `dipshits-design-system/CLAUDE.md` | Full brand brief — read this before touching any visual output |

> **Note:** `index.html` currently links `colors_and_type.css` (missing). New pages should link `dipshits-design-system/tokens.css` instead.

## Design system in practice

Load tokens and Phosphor icons:

```html
<link rel="stylesheet" href="dipshits-design-system/tokens.css"/>
<script src="https://unpkg.com/@phosphor-icons/web@2.1.1"></script>
```

**Type pattern** — always stack script eyebrow → display headline → body:

```html
<span class="ds-eyebrow-script">say hi to</span>
<h1 class="ds-mega">CRUNCH LOUD.<br/>DIP LOUDER.</h1>
<p class="ds-body-lg">Wildly fresh dips. Ridiculously crunchy chips.</p>
```

**Core visual rules (full rules in `dipshits-design-system/CLAUDE.md`):**

- Background is always `--tortilla` (`#FFF6E5`). Never white.
- Every layout needs at least 3 saturated colors.
- Shadows are flat hard offsets (`6px 6px 0 var(--ink)`). Never blurry on UI.
- Borders are 3–4px solid `--ink`. Cards look punched out of a cereal box.
- Key elements tilt −4° to +6°. Nothing is perfectly orthogonal.
- Buttons are pills with hard shadow; hover lifts + jiggles; press collapses the shadow.
- Motion: 140–280ms, `--ease-bounce` (`cubic-bezier(0.34, 1.56, 0.64, 1)`). Always respect `prefers-reduced-motion`.

**Component classes from `tokens.css`:** `.ds-button`, `.ds-card`, `.ds-sticker`, `.ds-pill`, `.ds-serape-band`, `.ds-container`, `.ds-section`.

**Hard nos:** white backgrounds, pure `#000`, blurred shadows on UI, gray icons, two-color-only layouts, center-everything page layouts.
