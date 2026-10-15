# Workflow: Design From Scratch

Use when building a new site, page, or app UI with no established design.

1. **Inspect the workspace.** Framework, styling method, UI/icon libraries, existing assets, README/brand docs. Reuse what exists; do not add dependencies without reason.
2. **Gather facts.** Product, audience, primary task, page list, available real content/assets. List assumptions. Ask only blocking questions (max 2-3).
3. **Write the brief** (template in SKILL.md Step 2). Include a "competitor-swap test": could the headline/brief describe another company? If yes, sharpen.
4. **Choose the concept** from purpose (editorial, corporate, product-led, technical, data-dense, luxury, portfolio, commerce, docs, playful).
5. **Define tokens** (color, type, space, radius, shadow, layout widths, motion). Size the system to the project: 6-10 tokens for one page, more for an app.
6. **Structure content** top-down: page goal -> sections in order of user need -> per-section purpose (one sentence each). Delete sections with no purpose.
7. **Build mobile-first or content-first** with semantic HTML, then layout, then tokens, then states. Keep components small and reusable.
8. **Cover states**: hover, focus-visible, active, disabled, loading, error, empty, success.
9. **Placeholders**: mark any missing real content, e.g. `[Real customer quote pending]`. Never fabricate proof.
10. **Run `workflows/inspect-and-refine.md`.** Do not stop at "it compiles".
11. **Score** with `tests/quality-scorecard.md` and write the final report (format in SKILL.md).

Common failure modes to self-check: default hero + three cards; one gradient everywhere; same section skeleton repeated; icon on every item; hover-only affordances; unlabeled inputs; invented numbers.
