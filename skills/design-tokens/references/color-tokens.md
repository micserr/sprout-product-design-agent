# Color Tokens — Complete Reference

All tokens below are in-theme (generate Tailwind utilities) unless marked **component-only**.

---

## Surface Tokens

Use `bg-{token}` for all surface backgrounds. These are in-theme tokens.

| Token | Class | Use when |
|---|---|---|
| `surface-white` | `bg-surface-white` | Page / canvas background — topmost, lightest layer |
| `surface-gray` | `bg-surface-gray` | Main gray canvas / app shell background |
| `surface` | `bg-surface` | Alias for surface-gray (same value) |
| `surface-adaptive` | `bg-surface-adaptive` | Cards, panels, inputs — translucent overlay for elevation |
| `surface-hover` | `bg-surface-hover` | Hover state on any surface |
| `surface-pressed` | `bg-surface-pressed` | Pressed / mousedown state on a surface |
| `surface-disabled` | `bg-surface-disabled` | Disabled container background |
| `surface-inverted` | `bg-surface-inverted` | Dark surface in light mode (tooltips, dark chips) |
| `surface-inverted-hover` | `bg-surface-inverted-hover` | Hover state on inverted surface |
| `surface-inverted-pressed` | `bg-surface-inverted-pressed` | Pressed state on inverted surface |
| `surface-active` | `bg-surface-active` | Selected / currently active item background |
| `surface-active-soft` | `bg-surface-active-soft` | Soft selected state — lighter than active |

---

## Semantic Color Families

Seven families: `brand` · `success` · `information` · `danger` · `pending` · `caution` · `accent`

Each family has 9 tokens following the same modifier pattern:

| Modifier | Tailwind class | Use when |
|---|---|---|
| `{family}` | `bg-{family}` | Filled background for this semantic state |
| `{family}-hover` | `bg-{family}-hover` | Hover on filled background |
| `{family}-pressed` | `bg-{family}-pressed` | Pressed state on filled background |
| `{family}-subtle` | `bg-{family}-subtle` | Soft/tinted background for subtle indicators |
| `{family}-subtle-hover` | `bg-{family}-subtle-hover` | Hover on subtle background |
| `{family}-subtle-pressed` | `bg-{family}-subtle-pressed` | Pressed state on subtle background |
| `{family}-text` | `text-{family}-text` | Text color on or near this semantic state |
| `{family}-text-hover` | `text-{family}-text-hover` | Text color on hover |
| `{family}-text-pressed` | `text-{family}-text-pressed` | Text color on press |

### Full token list per family

**`brand`** (kangkong-based green — primary actions, brand identity)
`bg-brand` · `bg-brand-hover` · `bg-brand-pressed` · `bg-brand-subtle` · `bg-brand-subtle-hover` · `bg-brand-subtle-pressed` · `text-brand-text` · `text-brand-text-hover` · `text-brand-text-pressed`

**`success`** (kangkong-based — positive outcome, saved, complete)
`bg-success` · `bg-success-hover` · `bg-success-pressed` · `bg-success-subtle` · `bg-success-subtle-hover` · `bg-success-subtle-pressed` · `text-success-text` · `text-success-text-hover` · `text-success-text-pressed`

**`information`** (blueberry-based — info, help, neutral notice)
`bg-information` · `bg-information-hover` · `bg-information-pressed` · `bg-information-subtle` · `bg-information-subtle-hover` · `bg-information-subtle-pressed` · `text-information-text` · `text-information-text-hover` · `text-information-text-pressed`

**`danger`** (tomato-based — errors, destructive actions, delete)
`bg-danger` · `bg-danger-hover` · `bg-danger-pressed` · `bg-danger-subtle` · `bg-danger-subtle-hover` · `bg-danger-subtle-pressed` · `text-danger-text` · `text-danger-text-hover` · `text-danger-text-pressed`

**`pending`** (mango-based — loading, in review, not yet complete)
`bg-pending` · `bg-pending-hover` · `bg-pending-pressed` · `bg-pending-subtle` · `bg-pending-subtle-hover` · `bg-pending-subtle-pressed` · `text-pending-text` · `text-pending-text-hover` · `text-pending-text-pressed`

**`caution`** (carrot-based — warnings, needs attention)
`bg-caution` · `bg-caution-hover` · `bg-caution-pressed` · `bg-caution-subtle` · `bg-caution-subtle-hover` · `bg-caution-subtle-pressed` · `text-caution-text` · `text-caution-text-hover` · `text-caution-text-pressed`

**`accent`** (wintermelon-based — highlights, secondary brand)
> Note: Accent bridge vars use `accent-fill` naming internally (to avoid shadcn-vue `--accent` conflict) but Tailwind classes are still `bg-accent`, `bg-accent-hover`, etc.

`bg-accent` · `bg-accent-hover` · `bg-accent-pressed` · `bg-accent-subtle` · `bg-accent-subtle-hover` · `bg-accent-subtle-pressed` · `text-accent-text` · `text-accent-text-hover` · `text-accent-text-pressed`

---

## Control Tokens

For interactive form controls (inputs, checkboxes, toggles):

`bg-control` · `bg-control-hover` · `bg-control-pressed`

---

## Text Tokens (Component-Only)

**These do NOT generate Tailwind utilities.** Use as component classes: `class="text-strong"`.

| Class | Use when |
|---|---|
| `text-strong` | Primary content, headings — highest emphasis |
| `text-supporting` | Secondary / supporting copy |
| `text-base` | Default body text |
| `text-weak` | Tertiary / hint / placeholder text |
| `text-disabled` | Disabled text |
| `text-on-fill-disabled` | Disabled text on filled/colored backgrounds |
| `text-inverted` | Text on dark/inverted surfaces — highest emphasis |
| `text-inverted-base` | Default text on inverted surfaces |
| `text-inverted-weak` | Muted text on inverted surfaces |
| `text-inverted-disabled` | Disabled text on inverted surfaces |

---

## Border Tokens (Component-Only)

**These do NOT generate Tailwind utilities.** Always pair `border` (width) + the color class.

```html
<div class="border border-base">...</div>
<div class="border border-weak">...</div>
```

| Class | Use when |
|---|---|
| `border-strong` | High-emphasis borders, focus rings |
| `border-supporting` | Secondary border emphasis |
| `border-base` | Default border — most common |
| `border-base-hover` | Border color on hover |
| `border-base-pressed` | Border color on press |
| `border-weak` | Subtle dividers, hairlines |
| `border-disabled` | Disabled element border |
| `border-on-fill-disabled` | Disabled border on filled/colored background |

---

## Outline Tokens (Component-Only)

Same values as border tokens but for `outline-color`. Use with `outline` + the class:

`.outline-strong` · `.outline-supporting` · `.outline-base` · `.outline-base-hover` · `.outline-base-pressed` · `.outline-weak` · `.outline-disabled` · `.outline-on-fill-disabled`

---

## Layout — Max-Width Tokens

In `@theme` — generates `max-w-*` Tailwind utilities:

| Class | Value | Use for |
|---|---|---|
| `max-w-content-sm` | 640px | Narrow: forms, auth pages, article text |
| `max-w-content-md` | 1000px | Standard: dashboards, settings, most page bodies |
| `max-w-content-lg` | 1320px | Wide: landing pages, full-width tables, marketing |
| `max-w-content-full` | 100% | Edge-to-edge: full-bleed sections, hero backgrounds |
