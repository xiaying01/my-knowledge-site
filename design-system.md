# Design Tokens — 湾区华人财务规划顾问

Extracted per `design-system-extract`. Machine-readable source of truth lives in `tokens/*.css`; this file is the human-readable export.

## Sources used

| Source | Type | What was read |
|---|---|---|
| `理财顾问 Landing Page.dc.html` | Built artefact (this project) | Every inline style value, post-review |
| `uploads/ai-slop-check.md` review pass | Audit | Palette consolidation, 4/8 spacing snap |
| `uploads/hierarchy-rhythm-review.md` review pass | Audit | Type scale, section rhythm, CTA hierarchy |

No codebase, Figma file, or brand guide was supplied. Every value below is read off the artefact — none invented.

---

## Colors

### Brand

| Token | Value | Source name | Usage |
|---|---|---|---|
| `--green-900` | `#12433a` | accent | Primary CTA fill, emphasised pricing card, links, wordmark |
| `--green-700` | `#2b6d5d` | accent hover | Link hover, eyebrow labels |
| `--green-400` | `#4d7f70` | — | Border on the green surface only |
| `--green-300` | `#86ab9f` | — | List dashes on green |
| `--green-200` | `#bfd4cd` | — | Muted text on green |
| `--green-100` | `#cfe0da` | — | Badge text on green |
| `--green-050` | `#e6efec` | — | Body text on green |

No dark/light theme variants are defined — the source has one theme.

### Semantic (success / warning / error / info)

**Not defined.** The source has no forms, no validation, no status states. This is a gap for the user to decide, not something to fill silently — see Gaps.

### Neutral scale

Three ink steps and three line steps, cool-neutral tone. This is not a 9–11 step ramp; the source genuinely uses six neutrals and no more.

| Token | Value | Usage | Contrast on white |
|---|---|---|---|
| `--ink-900` | `#1a1f1c` | Headings | 15.9:1 |
| `--ink-700` | `#464e49` | Body | 8.6:1 |
| `--ink-500` | `#5f6763` | Meta / captions | 5.4:1 — lightest text permitted |
| `--line-200` | `#e2e6e3` | Section + card borders |
| `--line-300` | `#d7dcd9` | Media and panel borders |
| `--line-400` | `#cdd3d0` | Secondary button border |

### Surfaces

| Token | Value | Usage |
|---|---|---|
| `--surface-page` | `#ffffff` | Page ground |
| `--surface-alt` | `#f5f7f6` | Alternating sections |
| `--surface-card` | `#ffffff` | Cards on `--surface-alt` |
| `--surface-accent` | `#12433a` | The one emphasised block per page |
| `--surface-header` | `rgba(255,255,255,0.92)` | Sticky header, with `blur(8px)` |
| `--mist-100` / `--mist-200` | `#f1f4f2` / `#e9ecea` | Image-placeholder stripe only |

No overlay/scrim token — the source has no modals.

---

## Typography

### Families

```
--font-display: "Noto Serif SC", Songti SC, serif;
--font-body:    "Noto Sans SC", "PingFang SC", sans-serif;
--font-mono:    ui-monospace, SFMono-Regular, Menlo, monospace;
```

Loaded from Google Fonts. Mono is a system stack — no webfont.

### Sizes (the actual scale in use)

`13 · 14 · 16 · 18 · 20 · 24 · 40` plus three fluid display sizes:

| Token | Value |
|---|---|
| `--text-h1` | `clamp(32px, 5.2vw, 58px)` |
| `--text-h2` | `clamp(26px, 3.2vw, 38px)` |
| `--text-lead` | `clamp(17px, 1.6vw, 20px)` |

### Weights (only those loaded)

`300` light — wordmark sub-label only · `400` regular — body · `500` medium — small emphasis · `600` semibold — all display type on light grounds · `700` bold — **display type on `--surface-accent` only** (`--weight-bold-on-accent`): the emphasised pricing card's title and price. CJK strokes thin optically when reversed out of deep green; 700 there matches the apparent weight of 600 on white. 700 on a light ground is a defect.

### Line heights

| Token | Value | Applies to |
|---|---|---|
| `--leading-h1` | `1.28` | h1 |
| `--leading-heading` | `1.35` | h2 |
| `--leading-card-heading` | `1.45` | Card titles |
| `--leading-body` | `1.7` | All body copy |

### Letter spacing

`--tracking-h1: -0.01em` (display only) · `--tracking-eyebrow: 0.16em` (13px labels) · `--tracking-wordmark: 0.02em` · `0.1em` on the badge.

### Named text styles

The source doesn't name them; these are the recurring combinations:

| Style | Definition |
|---|---|
| Display / H1 | display · 600 · `--text-h1` · 1.28 · −0.01em · max 20ch |
| Section / H2 | display · 600 · `--text-h2` · 1.35 · max 22ch |
| Card title | display · 600 · 20px · 1.45 |
| Price | display · 600 · 40px |
| Lead | body · 400 · `--text-lead` · 1.7 · max 52ch |
| Body | body · 400 · 16px · 1.7 |
| Meta | body · 400 · 14px · `--ink-500` |
| Eyebrow | body · 400 · 13px · 0.16em · `--green-700` |
| Mono ID | mono · 14px · `--green-900` |

---

## Spacing

Single 4/8 scale, inset and between-component alike:

`4 · 8 · 12 · 16 · 24 · 32 · 40 · 48 · 64 · 80 · 104`

Composition tokens derived from it:

| Token | Value |
|---|---|
| `--section-padding-y` | `clamp(56px, 8vw, 104px)` |
| `--section-padding-x` | `clamp(20px, 5vw, 72px)` |
| `--content-max` | `1180px` |
| `--measure-body` | `52ch` |
| `--measure-heading` | `22ch` |
| `--gap-eyebrow-heading` | `16px` |
| `--gap-heading-subcopy` | `24px` |
| `--gap-heading-content` | `48px` |
| `--gap-card-grid` | `clamp(24px, 3vw, 44px)` |
| `--padding-card` | `32px` |

---

## Radii and shadows

**Radii — two values, not five:** `--radius-sm: 2px` (buttons, cards, media) and `--radius-pill: 999px` (the single outlined badge). `0` is never used explicitly.

**Shadows — none.** There is no elevation scale. Separation is 1px borders plus surface tone. Recorded as `--shadow-none: none` so consumers can't invent one by accident.

---

## Other tokens

| Category | Value | Note |
|---|---|---|
| Duration | `--duration-fast: 120ms`, `--duration-base: 200ms` | Hover color only |
| Easing | `--ease-standard: cubic-bezier(0.2, 0, 0, 1)` | |
| Blur | `--header-blur: blur(8px)` | Sticky header, the only blur |
| Border width | `1px` everywhere | Weight varies by tone, never by px |
| Container | `1180px` | |
| Z-index | Only `10` (sticky header) | No scale defined |
| Breakpoints | **None** | Layout reflows via `auto-fit` / `clamp()`; no media queries exist in the source |

---

## Findings

### Gaps — the user's decisions, not filled here

1. **Semantic colors** (success / warning / error / info + their tinted backgrounds). Nothing in the source implies them. Needed the moment a contact form, booking confirmation, or client portal exists.
2. **Form tokens** — input height, focus ring, disabled state, placeholder color. No inputs exist yet; the booking flow hands off to Calendly.
3. **Elevation** — if a future surface needs a dropdown or modal, there is no shadow language to inherit. Recommend staying with borders and a scrim rather than introducing shadows.
4. **Z-index scale** — one value in use; formalise before adding overlays.
5. **Breakpoints** — deliberately absent. Formalise only if a layout can't be expressed with `auto-fit`.
6. **Neutral ramp depth** — six neutrals cover the current surface. A data-dense product (tables, dashboards) would need intermediate steps.

### Inconsistencies found and consolidated

| What | Before | After |
|---|---|---|
| Warm greys | 8 near-identical values (`#4a4740`, `#3b3831`, `#56534b`, `#6b665c`, `#8a8478`, `#7c766a`…) invented inline | 3 cool-neutral ink tokens |
| Accent greens | 6 values on drifting hues | One hue family, 7 steps |
| Page ground | Cream `#fbfaf8` + pure-white blocks, contradicting the "clean white" brief | White page / `#f5f7f6` alternation |
| Type sizes | 15 / 15.5 / 16.5 / 17 / 19 / 21 / 23px mixed with 13 / 14 / 16 | Snapped to the 7-step scale |
| Spacing | `15px`, `18px`, `22px`, `26px`, `38px`, `52px`, `108px` off-grid | 4/8 grid |
| Section rhythm | Heading→content gaps of 56 / 24 / 16 / 20px | 16 / 24 / 48 fixed |
| Meta text contrast | `#767d79` at 4.0–4.25:1 on small type | `#5f6763` at 5.4:1 |

### Resolved

- **700 weight** — previously loaded but unused. Now defined as `--weight-bold-on-accent`, scoped to display type on the deep-green surface (optical compensation for reversed CJK). Applied in `PricingCard` (emphasis), the website UI kit, and the live landing page.

### Recommended next steps

1. Review the two contrast-floor decisions (`--ink-500` as the lightest text; no shadow language).
2. Decide the semantic-color set before the first form ships.
3. Supply a logo and the WeChat QR image so `assets/` stops being empty.
