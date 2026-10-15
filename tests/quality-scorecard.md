# Design Quality Scorecard

A decision aid for the agent and reviewer, **not** an objective measure of art. Each score must cite evidence (screenshot, selector, measured value). Do not fabricate numbers; if unverified, write "unverified" and do not score it as 4+.

## Scale
0 = absent/broken | 1 = poor | 2 = weak | 3 = acceptable | 4 = good | 5 = excellent

## Categories
Critical (C) categories gate release. Others are weighted equally in the average.

| # | Category | C | Poor (0-2) | Acceptable (3) | Excellent (5) |
|---|---|---|---|---|---|
| 1 | Purpose & audience fit | C | Design ignores primary task or audience | Task supported but generic | Every section serves the objective; tone fits audience |
| 2 | Originality & product specificity | C | Interchangeable with any competitor; invented proof | Some specific content, some filler | Copy/visuals clearly about this product; no fabricated claims |
| 3 | Hierarchy & composition | C | No clear first/second read; uniform sections | Hierarchy present, repetitive composition | Squint test passes; composition fits content; coherent rhythm |
| 4 | Typography & readability | C | Faint/tight/over-long text; many fonts | Readable, roles loosely defined | Clear roles, comfortable measure/leading, deliberate type choice |
| 5 | Color & contrast | C | Failing contrast; many unrelated colors | Passing contrast, palette loosely systematic | Deliberate palette, all pairs verified, states checked |
| 6 | Spacing & alignment |  | Inconsistent gaps; misaligned edges | Mostly consistent | Scale-based, clear grouping, strong alignment |
| 7 | Icon & decorative restraint |  | Effects stacked, emoji/icons everywhere | Some unjustified decoration | Every effect/icon has purpose; one icon system |
| 8 | Component consistency |  | Same thing styled several ways | Mostly consistent | Token-driven, full state coverage |
| 9 | Responsive behavior | C | Overflow/clipping on mobile | Works, with minor layout compromises | Purposeful layouts per width; 320px and 200% zoom OK |
| 10 | Accessibility | C | Missing labels/focus, failing contrast | AA mostly met, gaps noted | WCAG 2.2 AA met for audited scope; keyboard pass done |
| 11 | Interaction quality |  | Dead controls, no feedback | Basic feedback and states | Clear feedback, loading/error/empty handled, motion purposeful |
| 12 | Technical maintainability |  | Scattered values, global side effects | Reasonable structure | Tokens, reuse, minimal scope, tests/build pass |

## Release rule
Release when **all** hold:
1. Every critical (C) category >= 4.
2. Overall average >= 4.
3. No critical functionality or accessibility defect remains (fix these regardless of score).
4. Unverified items are disclosed.

Exceptions: a category may be marked N/A with a written reason (e.g. no forms exist, so form-related accessibility criteria are N/A). If constraints prevent reaching 4 (brand mandates a low-contrast color, legacy framework), document the constraint, the mitigation, and who decided. Accessibility *requirements* are not waivable by the agent; surface them to the user.

## Output template
```
Mode: rendered (Playwright, 1440/390) | code-only
| Category | Score | Evidence |
| ...      | ...   | ...      |
Average: x.x | Critical all >=4: yes/no | Blocking defects: none/list
Exceptions: ...
```
