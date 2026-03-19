# Typography Tokens

## Scale

Font sizes, line heights, and letter spacings are defined as CSS custom properties in `@theme`.

| Axis | Token range |
|---|---|
| Font size | `text-100` … `text-1000` (rem) |
| Line height | `leading-100` … `leading-1000` |
| Letter spacing | `tracking-densest` … `tracking-widest` |

**Default body size:** `0.875rem` (14px) = `text-300`

---

## Component Classes

Always use component classes instead of raw `text-{size}` utilities. They bundle size, weight, leading, and tracking into a single class.

### Body

| Class | Use for |
|---|---|
| `body` | Default body text (14px) |
| `body-medium` | Medium-weight body |
| `body-md` | Medium-size body (slightly larger) |
| `body-md-medium` | Medium-size, medium-weight body |
| `body-lg` | Large body text |
| `body-lg-medium` | Large, medium-weight body |

### Label

| Class | Use for |
|---|---|
| `label-xs` | Extra-small labels, tags, metadata |
| `label-xs-medium` | Extra-small medium-weight label |
| `label-sm` | Small labels |
| `label-sm-medium` | Small medium-weight label |

### Heading

| Class | Use for |
|---|---|
| `heading-xl` | Page-level hero titles |
| `heading-lg` | Section headings |
| `heading-md` | Card / panel titles |
| `heading-sm` | Sub-section titles |
| `heading-xs` | Compact / tight headings |

### Subheading

| Class | Use for |
|---|---|
| `subheading-sm` | Small subheading beneath a heading |
| `subheading-xs` | Extra-small subheading |

### Utility

| Class | Use for |
|---|---|
| `caption` | Small supporting / meta text beneath content |
| `caption-medium` | Medium-weight caption |
| `overline` | ALL CAPS label above a heading or section |
| `code` | Monospace code inline or block |

### Prose Scope

| Class | Use for |
|---|---|
| `typography` | Wrapper for long-form prose content — applies sensible defaults to `<p>`, `<h1>`–`<h6>`, `<ul>`, etc. |

---

## Font Families

Defined as CSS custom properties in `:root`:

| Var | Usage |
|---|---|
| `--font-heading` | Applied to heading component classes |
| `--font-body` | Applied to body and label component classes |

Do not reference these vars in component code — they're applied automatically by the component classes above.

---

## Usage Rules

- **Always use component classes** over raw `text-{size}` utilities
- **Never mix** font size + weight manually when a component class exists
- **`typography` wrapper** is for long-form content only (article body, docs, rich text) — not UI chrome
- **`overline`** implies small, spaced, uppercase text — do not apply uppercase via CSS separately
