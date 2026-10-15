# Layout and Components

Contents: Layout techniques | Component rules | States matrix | Forms | Tables | Navigation | Dashboards | Empty/loading/error

## Layout techniques
- CSS Grid for two-dimensional page layout; Flexbox for one-dimensional alignment. Use `gap`, not margin hacks.
- Fluid grids: `grid-template-columns: repeat(auto-fit, minmax(min(100%, 18rem), 1fr))` avoids breakpoint sprawl for card/list collections.
- Constrain prose with `max-width: 65ch`; wide layouts with a `--content-wide` wrapper plus `padding-inline`.
- Use `min-height`, not fixed heights; `aspect-ratio` for media; `object-fit: cover` with intentional focal points.
- Sticky headers: account for height with `scroll-padding-top` so focused items are not obscured (WCAG 2.4.11).
- Keep DOM order equal to reading order; avoid `order` tricks that desync focus from visuals.

## Component rules
Every component needs a purpose and a consistent tie to the system (tokens for color, radius, spacing, type).
- **Buttons**: one primary per view region; secondary = outline/subtle; destructive = distinct semantic color + confirmation. Min target 24x24px (prefer 40-48px on touch). Verb-led labels.
- **Links**: distinguishable from text without relying on color alone (underline by default in body copy).
- **Cards**: group independent items; consistent padding; one clickable region (whole-card link) with a single focus target.
- **Dialogs**: focus moves in, is trapped, returns on close; Esc closes; labelled by title; backdrop not the only dismissal.
- **Dropdowns/menus**: keyboard arrows, Esc, `aria-expanded`; prefer native `<select>`/`<details>`/`<dialog>`/popover when sufficient.
- **Alerts/toasts**: use `role="status"` or `role="alert"` appropriately; do not auto-dismiss critical messages.
- **Footers/secondary nav**: organized, real links only.

## States matrix (check each that applies)
| State | Requirement |
|---|---|
| Default | Clearly identifiable as interactive (if it is) |
| Hover | Subtle change; not the only affordance (touch has no hover) |
| Focus-visible | Ring >= 3:1, not clipped, not hidden by sticky UI |
| Active/pressed | Immediate feedback |
| Disabled | Muted but legible; explain why if non-obvious; use `disabled` or `aria-disabled` |
| Loading | Indicator + preserved layout; prevent double submit |
| Error | Message text + icon/pattern, not color only; linked to field |
| Empty | Explain what belongs here + next action |
| Success | Confirm outcome; say what happens next |

## Forms
- Visible persistent `<label for>`; placeholders are examples only.
- Group related fields (`fieldset`/`legend`); mark required/optional consistently.
- Correct `type`, `inputmode`, `autocomplete` attributes.
- Validation: on blur/submit, not on every keystroke; inline message beside the field, `aria-describedby`, summary at top for long forms; do not clear user input on error.
- Single-column by default; multi-column only for short related pairs (city/zip).
- Submit button states: idle, loading, success/failure.

## Tables and data
- Use real `<table>` with `<th scope>`, caption or heading association.
- Right-align numbers, use tabular figures (`font-variant-numeric: tabular-nums`), consistent decimals/units.
- Sticky header for long tables; zebra or row dividers (not both heavy); adequate row height (>= 40px for touch-capable).
- Narrow screens: wrap in `overflow-x: auto` container with visible affordance, or reflow to stacked rows for few columns. Never let the page body scroll sideways.
- Sorting/filtering controls labelled and keyboard operable.

## Navigation
- Primary nav: <= 7 top-level items; current page indicated (`aria-current="page"`) with more than color.
- Mobile: defined pattern (menu button with `aria-expanded`, or visible bottom/tab nav for apps); targets large enough; no hover-only reveal.
- Skip link to `main` on content-heavy pages.

## Dashboards
Structure by task: (1) what needs attention now, (2) key trend, (3) detail table/filters, (4) secondary metrics. Each chart answers a named question; label axes/units/time range; color-blind-safe series with direct labels or patterns. Sample data must be labelled as sample.

## Loading, empty, error pages
Design them. Skeletons should match final layout to avoid shift. Error pages: say what happened, what to do, and offer a way out. Do not show raw stack traces or "Something went wrong" with no action.
