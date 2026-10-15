# Workflow: Improve an Existing Interface

Use for redesigns, modernization, audits, "make it look better", or removing generic styling. Preserve stack, behavior, routes, and brand unless told otherwise.

1. **Inspect**: read the relevant files (components, styles, tokens, theme, assets). Note framework, CSS approach, component library, brand colors/fonts, tests. Run the app if possible and capture "before" views (desktop + mobile).
2. **Diagnose** with `references/visual-review-checklist.md` and `references/anti-pattern-catalog.md`. Produce a ranked issue list using the triage order (function > a11y > layout/responsive > hierarchy > consistency > decoration > polish). For each issue: evidence (file/selector or screenshot), impact, proposed fix, effort.
3. **Respect the brand.** If an established identity exists (palette, gradient, typeface, mascot), keep it and refine around it. A brand gradient or playful palette is not a defect.
4. **Choose the smallest effective scope.** Prefer: tokenizing existing values, fixing hierarchy/spacing/type, flattening needless containers, repairing states and contrast, over rewriting components. Do not rewrite a working interface needlessly.
5. **Plan** the changes in 5-10 bullets, grouped by area. For large redesigns, share the plan before implementing.
6. **Implement incrementally.** Centralize repeated values; avoid broad global CSS edits; keep selectors specific; keep routes, props, form logic, and tests intact.
7. **Regression check**: run build, lint, unit/e2e tests; view affected pages and adjacent pages sharing components.
8. **Run `workflows/inspect-and-refine.md`**, capture "after" views, compare with "before".
9. **Report**: what changed and why, what was deliberately left alone, checks run, unverified items, follow-ups.

Guardrails: no new framework/styling system; no dependency adds for decoration; no behavior changes mixed into a visual pass unless required and disclosed.
