# Accessibility and Responsive Design

Contents: Standard & status | WCAG 2.2 AA checklist | Keyboard | Semantics | Motion | Responsive | Testing methods | Limits

## Standard & status
Target **WCAG 2.2 Level AA** where applicable (W3C Recommendation; WCAG 2.2 removed SC 4.1.1 and added criteria such as 2.4.11 Focus Not Obscured (Minimum) and 2.5.8 Target Size (Minimum) at AA). Legal requirements vary by jurisdiction; this file is engineering guidance, not legal advice. Re-check the W3C pages if a newer version has been published. Source pages: w3.org/TR/WCAG22/ and w3.org/WAI/WCAG22/Understanding/.

## WCAG 2.2 AA checklist (design-relevant)
| SC | Requirement | How to check |
|---|---|---|
| 1.1.1 | Meaningful images have alt; decorative `alt=""` | Inspect |
| 1.3.1 | Structure in markup (headings, lists, table headers, labels) | DOM / a11y tree |
| 1.3.5 | Input purpose via `autocomplete` | Inspect |
| 1.4.1 | No info by color alone | Grayscale view |
| 1.4.3 | Text contrast 4.5:1 (3:1 large) | Script / tool |
| 1.4.4 | Text resizes to 200% without loss | Browser zoom |
| 1.4.10 | Reflow at 320 CSS px, no 2-D scroll (except data tables, maps etc.) | 320px viewport |
| 1.4.11 | Non-text contrast 3:1 for controls and graphics | Tool |
| 1.4.12 | Text spacing overrides do not break layout | Apply spacing bookmarklet |
| 1.4.13 | Hover/focus content dismissible, hoverable, persistent | Manual |
| 2.1.1 / 2.1.2 | Keyboard operable, no trap | Tab through |
| 2.4.1 | Bypass blocks (skip link/landmarks) | Manual |
| 2.4.3 | Focus order logical | Tab through |
| 2.4.4 / 2.4.6 | Link purpose; descriptive headings/labels | Review |
| 2.4.7 | Focus visible | Tab through |
| 2.4.11 | Focused element not fully hidden by sticky/overlay content | Tab with sticky header |
| 2.5.8 | Targets >= 24x24 CSS px (or spacing/other exception) | Measure |
| 3.2.x | Predictable behavior | Review |
| 3.3.1 / 3.3.2 / 3.3.3 | Errors identified, labels/instructions, suggestions | Submit bad data |
| 3.3.7 / 3.3.8 | Redundant entry; accessible authentication (2.2 additions) | Review |
| 4.1.2 | Name, role, value for custom controls | a11y tree |
| 4.1.3 | Status messages announced | Screen reader / ARIA live |

Distinguish: the table above is **requirement**. Choices like "prefer 44px targets" or "underline links" are **best practice** unless stated otherwise.

## Keyboard & focus
- Every interactive element reachable by Tab, operable by Enter/Space (native elements first).
- Use `:focus-visible` with a ring, e.g. `outline: 2px solid var(--color-focus-ring); outline-offset: 2px;`. Never `outline: none` without replacement.
- Modals trap and restore focus; menus support arrows/Esc.

## Semantics
Landmarks (`header nav main aside footer`), one `h1`, no skipped heading levels for styling reasons (style with CSS), `button` for actions and `a` for navigation, lists for lists, `table` for tabular data. ARIA only to fill gaps native HTML cannot.

## Motion
Honor `prefers-reduced-motion: reduce` (remove or simplify non-essential motion). Avoid flashing > 3 times/second (SC 2.3.1). Auto-playing motion > 5s needs pause control (SC 2.2.2).

## Responsive design
Source: web.dev Responsive Web Design Basics. Core: `<meta name="viewport" content="width=device-width, initial-scale=1">`, fluid layouts, relative units, flexible media, content-driven breakpoints.
Do not target named devices. Add a breakpoint where the layout breaks, e.g. nav no longer fits or measure too long.

Review at least 320, ~390, ~768, ~1024, ~1440 CSS px, plus 200% zoom and landscape mobile:
- Nav collapse behavior and menu usability
- Heading and paragraph wrapping; no clipped or colliding text
- Button size, touch spacing
- Grid column changes, image cropping, aspect ratios
- Tables/dense data (scroll container or reflow)
- Forms, validation messages, on-screen keyboard overlap
- No horizontal page overflow (`document.documentElement.scrollWidth <= innerWidth`)
- Spacing/hierarchy preserved
- Reading order and focus order match

Handy CSS: `clamp()` for type/space, `min()`/`max()`, container queries for components, `dvh` instead of `vh` for mobile viewport, `overflow-wrap: anywhere` for long strings, `scroll-margin-top` for anchored headings.

## Testing methods
Automated (catches roughly a third to half of issues at best): axe-core, Lighthouse, pa11y, Playwright + @axe-core/playwright, eslint-plugin-jsx-a11y. Manual: keyboard-only pass, 200% zoom, 320px reflow, grayscale/forced-colors check, screen-reader smoke test (VoiceOver/NVDA) when possible.

## Limits
Without a browser, you can only review code: check semantics, tokens, contrast math, and CSS logic. State this explicitly. Automated tools do not certify compliance.
