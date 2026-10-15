# Visual Design Principles

Contents: 1 Hierarchy | 2 Composition & grids | 3 Spacing | 4 Alignment & proximity | 5 Contrast & emphasis | 6 Rhythm | 7 Density | 8 Poor vs improved

Sources synthesized: Nielsen Norman Group visual-design articles (scale, visual hierarchy, balance, contrast, gestalt, color), U.S. Web Design System tokens, web.dev responsive basics. Wording is original. Verify against current sources when citing.

## 1. Hierarchy
Hierarchy tells the visitor what to read first, second, third. Tools, strongest first: size, weight, contrast, position, whitespace, color, containers. Use at most 3 emphasis levels per view. If everything is emphasized, nothing is.
Test: squint at the screenshot (or blur it). The top 2 things should still be identifiable.

## 2. Composition & grids
- Pick a grid that fits content (12-col for marketing, fixed sidebar + fluid main for apps, single readable column for docs).
- Consistent gutters and margins; define max content widths per role (prose ~65ch, wide layouts ~1200-1280px).
- Asymmetry (e.g. 5/7 split) is useful when one side is primary. Do not force it.
- Preserve DOM reading order when layout shifts at breakpoints.

## 3. Spacing
Use one scale (4px or 8px base, or the project's). Three distinct spacing jobs:
1. Within a component (tight)
2. Between related elements (medium)
3. Between sections (large)
Space communicates grouping. Too little = clutter; too much = disconnected, empty-feeling page.

## 4. Alignment & proximity
Align to a few strong edges. Items that belong together sit closer than items that do not (proximity). Fix alignment before adding borders or backgrounds.

## 5. Contrast & emphasis
Contrast in size, weight, color, and density creates focus. Reserve the accent color for actions and key information; if the accent appears everywhere it stops guiding.

## 6. Rhythm
Alternate dense and airy, text and media, narrow and wide, with intent. Repetition builds identity; unbroken sameness (every section: heading + subtitle + 3 cards) builds monotony.

## 7. Density by context
| Context | Density | Notes |
|---|---|---|
| Marketing / editorial | Airy | Large type, generous space, one idea per section |
| SaaS product | Medium | Clear grouping, restrained chrome |
| Data / operations | Compact | Tables, small but readable type (>= 14px), strong alignment |
| Docs | Reading-first | Narrow measure, strong headings, code styling |

## 8. Poor vs improved (illustrative, not templates)
| Poor | Why | Improved |
|---|---|---|
| Hero: "Transform your workflow" + gradient blob + 3 identical cards | Generic, interchangeable, no product evidence | Hero names the product job ("Reconcile invoices against purchase orders in one view") beside a real product screenshot; below, a comparison table of before/after steps |
| Every section in a rounded shadowed card | Containers replace hierarchy; visual noise | Sections separated by spacing and a hairline; cards only for pricing tiers |
| Dashboard with 8 equal KPI tiles | No priority, no task | One primary metric + trend, a filtered table of items needing action, secondary metrics in a compact strip |
| 5 accent colors | No signal for what matters | One brand accent; semantic colors only for status |
