---
name: design-pro
description: Professional Web Design & Anti-AI-Slop. Use this skill BEFORE writing any UI code, and whenever the user asks to build, design, redesign, modernize, audit, or polish a website, landing page, portfolio, SaaS app, dashboard, admin panel, form, table, navigation, component, theme, or design system, or asks to remove generic "AI-looking" design. Use it even if the user never says "design" (e.g. "make me a homepage", "fix this page", "make it look better", "add a pricing section"). It enforces a purpose-first design brief, a deliberate token system, WCAG 2.2 AA accessibility, responsive checks, and a render-and-review loop so output is specific, consistent, and credible instead of template-generic.
---

# Design Pro — Professional Web Design & Anti-AI-Slop

**Principle:** Purpose before decoration. Hierarchy before components. Content before layout. Consistency before effects. Validation before "done".

You are acting as a design engineer, not a component generator. The goal is not to avoid AI help; it is to avoid generic, careless, or unconsidered output. Judge **observable quality** (specificity, hierarchy, consistency, usability). Never claim a site "is" or "is not" AI-generated.

## How to use this skill

1. Read this file fully. It contains every critical rule.
2. Follow the workflow in `workflows/` that matches the task:
   - New build: `workflows/design-from-scratch.md`
   - Existing UI: `workflows/improve-existing-interface.md`
   - After any substantial UI change: `workflows/inspect-and-refine.md`
3. Load a reference file only when you need depth:
   - `references/visual-design-principles.md` — hierarchy, composition, spacing, rhythm
   - `references/anti-pattern-catalog.md` — what to detect, why it hurts, when it is fine, how to fix
   - `references/typography-and-color.md` — type scales, palette process, tokens, contrast
   - `references/layout-and-components.md` — grids, component states, forms, tables, dashboards
   - `references/accessibility-and-responsive-design.md` — WCAG 2.2 AA specifics, responsive checks
   - `references/visual-review-checklist.md` — the per-project checklist
4. Before reporting completion, score the work with `tests/quality-scorecard.md`.

## Rule tiers (do not mix them up)

| Tier | Meaning | Examples |
|---|---|---|
| **Requirement** | Standards-based. Must be met (WCAG 2.2 AA where applicable). Not negotiable for style. | 4.5:1 text contrast, visible focus, labels on inputs, 24x24px targets |
| **Principle** | Established design practice. Break only with a stated reason. | One clear primary action per view, consistent spacing scale |
| **Heuristic** | Community taste. A signal to *review*, never an automatic ban. | Purple gradients, glassmorphism, three-card feature rows |
| **Project decision** | Depends on brand and purpose. Existing brand wins over this skill's taste. | Palette, typeface, density, tone |

A heuristic flagged in the catalog fails only when it is **unjustified**. A gradient, centered hero, card grid, shadow, or icon that genuinely serves the project passes.

## Step 0: Scope check (30 seconds)

- Tiny one-off fix (one button, one margin)? Apply the critical rules below, skip the full brief.
- New page, redesign, or system work? Run the full workflow.
- Existing repo? **Inspect first. Extend the existing stack, tokens, components, and brand.** Do not swap frameworks, add dependencies, or restyle globally unless asked.

## Step 1: Understand (before any code)

Read the relevant files, then answer in writing:
- What does the product do, who uses it, what is the single most important user task?
- What type is it: content, conversion, transactional, data-dense, operational, informational?
- What exists already: logo, palette, fonts, tokens, component library, design references?
- Stack: framework, styling method, icon set, UI library.

**Never invent** business facts, features, testimonials, customer logos, ratings, statistics, screenshots, pricing, or claims. If real content is missing, use clearly marked placeholders (e.g. `[Customer quote: pending]`) and say so in your report.

Ask the user a question only when a missing decision would materially change the result and cannot be responsibly inferred. Otherwise state your assumptions and proceed. Ask at most 2-3 questions at once.

## Step 2: Write a design brief (before coding)

Produce this brief (short, 10-20 lines) in your reply or a scratch file. Specificity is the test: if the brief could describe any company, rewrite it.

```
Objective:            what the page must achieve
Audience:             who, in what context/device
Brand personality:    3 adjectives + what it is NOT
Content hierarchy:    1st / 2nd / 3rd things a visitor must get
Primary action:       one; secondary actions listed
Layout concept:       one sentence naming the composition
Typography:           typefaces (or system stack) + why
Color:                brand accent, neutrals, semantic states + why
Imagery:              real assets / screenshots / typographic / none
Icons:                library in use, where icons are allowed
Shape & depth:        radius scale, borders vs shadows
Motion:               what animates and why (default: almost nothing)
A11y & responsive:    WCAG 2.2 AA, breakpoints driven by content
```

If the user supplied references, extract *useful traits* (hierarchy, density, proportion, interaction) and explain them. Do not clone another site's branding.

## Step 3: Choose a concept from purpose

Pick based on the project, not on the most common generated layout. Options (combine freely): editorial/magazine, restrained corporate, product-led SaaS, technical/developer, data-dense operational, luxury/premium, portfolio/case-study, retail/commerce, content-first docs, playful consumer. Do not pick the same concept every time. Do not force asymmetry or variety for its own sake.

## Critical rules

### A. Layout and content
1. Design around real content and the user journey. Every section must earn its place by serving the page objective.
2. Hierarchy comes from size, weight, spacing, alignment and contrast **before** containers. Reach for whitespace, dividers, and typography before cards.
3. Use cards only to group independent, scannable or interactive items. No card-inside-card without a clear reason. No rounded box around every section.
4. Match grid proportions to content priority. Equal columns for unequal content is a smell. Left-align text that people must scan; center sparingly.
5. Vary section composition when the content differs (split, comparison table, timeline, list, product view). Keep rhythm coherent.
6. Hero: say something specific and concrete about *this* product, show a real product view or meaningful content, and put the primary action in view. No vague headline that fits any company.
7. Dashboards: organize by the user's task and decision flow. No random metric cards, no invented data. Compact tables beat cards for dense comparison.

### B. Effects and decoration
8. Every gradient, glow, blur, shadow, border, blob, particle, or parallax needs a stated purpose (brand, hierarchy, state, depth). Otherwise remove it.
9. Do not stack effects (gradient + shadow + glow + border) on one element.
10. Effects must never reduce readability or contrast.

### C. Shape system
11. Define a deliberate radius scale (e.g. 0 / 4 / 8 / full) and use it by role. No arbitrary mixes. Pills only where the pill shape means something (tags, toggles), not for every button, nav item and label.

### D. Typography
12. Define roles: display, page heading, section heading, body, supporting, label/metadata, button/nav. Use as few families and sizes as the content needs.
13. Body: line-height about 1.5-1.7, measure about 45-80 characters, never faint gray-on-white. Headings must not wrap awkwardly or collide on mobile.
14. No ALL-CAPS micro-label on every section. No oversized heading used to hide weak content.
15. Inter, Roboto, and system fonts are fine when chosen on purpose. A fashionable pairing is not a substitute for hierarchy.

### E. Icons and emoji
16. Use an icon only when it communicates a recognizable action, state, or category. Prefer a text label when meaning is ambiguous.
17. No icon beside every heading/feature/paragraph. No emoji as UI icons. One icon set per project, consistent size, stroke, alignment, color.
18. Icon-only controls need an accessible name (`aria-label` or visually hidden text). Do not add an icon dependency just to decorate; reuse the one in the repo.

### F. Copy
19. Write concise, concrete copy about the real product. Avoid "revolutionary", "next-generation", "transform your workflow", repeated "Learn more"/"Get started" with no distinct meaning, and filler paragraphs.
20. No fake testimonials, fake logos, fake stats, fake ratings, fake screenshots. Use transparent placeholders.

### G. Imagery
21. Prefer real project assets, authentic screenshots, relevant photos, purposeful illustration, or clean typographic composition. No generic stock-style art, floating blobs as automatic hero art, or generated images showing fake UI text or nonexistent features.

### H. Motion
22. Animate only to communicate state change, give feedback, or clarify relationships. Do not animate every section on scroll. No bounce/elastic/floating by default.
23. Honor `prefers-reduced-motion`. Content and function must never depend on animation or delay access.

## Color and tokens

Process: brand personality and context -> inspect existing brand assets -> primary accent only with a credible reason -> neutral surfaces and text -> secondary colors only if needed -> semantic colors (success, warning, error, info) -> validate contrast -> check in real components and states.

- Small palette (one deliberate accent + restrained neutrals) beats many bright colors. Professional does not mean blue/black/white; pick what fits.
- Use semantic tokens (`--color-text-primary`, `--color-surface`, `--color-brand-primary`), adapted to the project's naming. Cover color, type, spacing, radius, shadow/elevation, layout widths, motion duration/easing.
- Do not scatter raw hex values through components when tokens would be maintainable. Do not over-engineer a token system for a tiny page.
- Details: `references/typography-and-color.md`.

## Accessibility requirements (WCAG 2.2 AA where applicable)

These are requirements, not taste:
- Text contrast >= 4.5:1 (normal) and >= 3:1 (large text), per SC 1.4.3. Includes muted text, placeholders, disabled-looking-but-readable labels, button text.
- Non-text contrast >= 3:1 for control boundaries/states and meaningful graphics (SC 1.4.11).
- Visible keyboard focus on every interactive element (SC 2.4.7) that is not hidden behind sticky headers (SC 2.4.11).
- Never convey status by color alone (SC 1.4.1).
- Every input has a programmatically associated visible label; placeholder is not a label (SC 1.3.1, 3.3.2, 4.1.2).
- Pointer targets >= 24x24 CSS px or meet the spacing exception (SC 2.5.8). Prefer larger for key mobile actions.
- Content reflows at 320 CSS px width without 2-D scrolling (SC 1.4.10); text resizes to 200% (SC 1.4.4).
- Use semantic HTML (`header`, `nav`, `main`, `button`, `a`, `table`, heading order). Logical focus and reading order.
- Respect `prefers-reduced-motion`.
Full list and test methods: `references/accessibility-and-responsive-design.md`.

## Responsive requirements

Review at mobile, tablet, desktop; do not just shrink desktop. Use fluid layouts, relative units, content-driven breakpoints (not device names), responsive media with stable aspect ratios, and a defined narrow-screen nav. Check heading wrap, button size, grid changes, image crop, dense tables (scroll container or reflow), forms and error messages, overflow/clipping/overlap, spacing, focus/reading order, zoom.

## Implementation rules

- Reuse existing dependencies, components, tokens. Smallest sensible scope of change.
- Centralize repeated values. Avoid broad global CSS edits that cause regressions.
- Preserve routes, behavior, semantic HTML, labels, and form logic.
- No dead controls, broken links, fake actions, or unusable form elements. If an action is not wired up, say so.
- Real content, not lorem ipsum, unless clearly marked as temporary.
- Every component gets its relevant states: default, hover, focus, active, disabled, loading, error, empty, success.
- Do not make non-interactive things look clickable. Do not trade usability for originality.

## Execution workflow (8 phases)

1. **Inspect**: task, repo, audience, existing UI, constraints.
2. **Diagnose** (existing UI): list the most consequential problems first. Do not rewrite a working interface needlessly.
3. **Plan**: write the brief (Step 2).
4. **Implement** in the existing stack and conventions.
5. **Inspect the result**: run the app/checks; look at the *rendered* interface when tools allow.
6. **Refine**: fix the most visible/consequential issues first; re-inspect.
7. **Verify**: goals, accessibility, responsive, consistency, function.
8. **Report** (format below).

Fix priority: (1) broken/misleading function, (2) accessibility and readability failures, (3) layout/responsive defects, (4) hierarchy and content structure, (5) design-system inconsistency, (6) unnecessary decoration, (7) minor polish. "It compiles" is not done.

## Honesty about verification

- Never claim you visually inspected a rendered page, ran an accessibility audit, or tested a breakpoint unless you actually did, and name the tool/viewport used.
- If you cannot render (no browser, no screenshot tool), say "code-level review only" and list what remains unverified.
- Do not fabricate scores, test results, contrast ratios, or Lighthouse numbers. Compute contrast or run a tool; otherwise mark as unverified.

## Rendered-review loop (when tools exist)

Capture desktop (~1440px) and mobile (~390px) -> inspect hierarchy, whitespace, alignment, type, color, rhythm -> check overflow, overlap, clipping, wrapping, inconsistent components -> check hover/focus/disabled/error states -> run automated a11y checks (axe, Lighthouse, or Playwright + axe) -> fix top issues -> recapture. See `workflows/inspect-and-refine.md` for commands.

## Scoring (decision aid, not objective art measurement)

Score 0-5 on the 12 categories in `tests/quality-scorecard.md`. Release when every critical visual category >= 4, overall average >= 4, and **no critical functionality or accessibility defect remains** (those must be fixed regardless of score). Document any exception where a criterion does not apply. Never invent numbers; scores are your reasoned judgment and must cite evidence.

## Final report format

```
Summary:        what changed and why (design decisions, not a file list only)
Direction:      the brief in 2-3 lines
Checks done:    exactly what was run/seen (viewports, tools, states)
Not verified:   anything you could not check
Scorecard:      category scores with one-line evidence (or "skipped: tiny change")
Open issues:    remaining defects, placeholders, assumptions needing user input
```

## Anti-goals (what this skill must not cause)

- Identical-looking sites. The skill sets a quality bar, not a template.
- Banning legitimate choices: brand gradients, playful palettes, centered heroes, cards, shadows, and icons are fine when they serve the project.
- Rewriting working UIs, swapping stacks, or ignoring an established brand.
