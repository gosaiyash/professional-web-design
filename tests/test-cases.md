# Test Cases

Purpose: check that the skill changes agent behavior without banning legitimate choices. Each case lists scenario, undesirable default, correct decision, expected observable result, and the verifying check.

How to run: give an agent the **Input** with and without the skill loaded; compare against **Expected result**. Record Pass/Fail with evidence in the scorecard. Pass = the agent's decision is justified for the project, not that a given pattern is absent.

Verifier key: VRC = `references/visual-review-checklist.md` section; SC = `quality-scorecard.md` category #; APC = `references/anti-pattern-catalog.md` entry; A11Y = `references/accessibility-and-responsive-design.md`.

---
### T01 Generic SaaS landing page
- **Input:** "Build a landing page for my invoice-matching SaaS."
- **Default:** Centered "Transform your workflow" headline, purple gradient, three identical icon cards.
- **Correct:** Brief names concrete job; hero states it with a product view or real content; features ranked; gradient only if brand-justified.
- **Expected:** Headline specific (fails competitor-swap if generic); no unjustified gradient; features not three equal cards unless equal weight; placeholders marked.
- **Verify:** APC A1, B1, F1; VRC 1-2; SC 2,3.

### T02 Every section in a rounded card
- **Input:** "Make this company homepage cleaner" (repo where each section is a rounded shadowed card).
- **Default:** Add more cards/shadows.
- **Correct:** Flatten; separate with spacing/hairlines; keep cards only for independent items.
- **Expected:** Fewer nested containers, one radius scale, hierarchy from type/space.
- **Verify:** APC C1-C4; VRC 2,5; SC 3,7.

### T03 Emoji beside every heading
- **Input:** "Add feature highlights."
- **Default:** Emoji before each heading.
- **Correct:** Remove emoji; use text/typography; icons only where meaning is carried, from the project's icon set.
- **Expected:** No emoji UI icons; any icon consistent and named if icon-only.
- **Verify:** APC E1-E3; VRC 5.

### T04 Five competing accent colors
- **Input:** "Pick colors for a legal-tech dashboard."
- **Default:** Blue, purple, orange, green, pink accents.
- **Correct:** One accent + neutrals + semantic status colors; contrast verified.
- **Expected:** Token palette with rationale; computed ratios.
- **Verify:** VRC 4; SC 5; typography-and-color.md.

### T05 Dashboard with invented metrics
- **Input:** "Create an admin dashboard."
- **Default:** Eight KPI cards with fake numbers and decorative charts.
- **Correct:** Task-led hierarchy; sample data clearly labelled; table for dense items; each chart answers a question.
- **Expected:** "Sample data" label, one primary metric, actionable table, labelled axes.
- **Verify:** APC J1-J3; VRC 1; SC 1,2.

### T06 Placeholder-only form labels
- **Input:** "Build a signup form."
- **Default:** Inputs with placeholder text only.
- **Correct:** Persistent visible labels, `autocomplete`, inline errors linked via `aria-describedby`.
- **Expected:** `<label for>` per field; error text not color-only.
- **Verify:** APC I1; A11Y 1.3.1, 3.3.1, 3.3.2; VRC 6,8.

### T07 Mobile clipping and table overflow
- **Input:** "Fix the mobile layout" (heading clipped, table overflows).
- **Default:** Shrink font to fit; hide overflow.
- **Correct:** Fluid type (`clamp`), wrapping rules, table in scroll container or reflow, test at 320/390.
- **Expected:** No horizontal page scroll; heading fully visible; table usable.
- **Verify:** A11Y 1.4.10; VRC 7; SC 9. Needs rendered check (Playwright overflow script).

### T08 Subtle but unreadable text
- **Input:** "Use light gray secondary text for a minimal look."
- **Default:** #AAA on white.
- **Correct:** Keep the minimal look at >= 4.5:1 (e.g. darker gray); explain the requirement.
- **Expected:** Computed ratio reported; text passes.
- **Verify:** A11Y 1.4.3; VRC 4; SC 5,10.

### T09 Brand genuinely needs a gradient
- **Input:** "Our brand uses a teal-to-violet gradient (see brand guide). Build the homepage."
- **Default (over-correction):** Remove gradient because "gradients are slop."
- **Correct:** Keep and use the brand gradient purposefully (hero background or key accent), ensure text contrast on it.
- **Expected:** Gradient present, tokenized, contrast verified; no extra decorative effects.
- **Verify:** SKILL.md rule tiers (heuristic vs project decision); SC 1,5. **Fails if** the agent strips the brand gradient.

### T10 Playful consumer product
- **Input:** "Landing page for a kids' language-learning app."
- **Default (over-correction):** Muted corporate palette.
- **Correct:** Expressive colors, friendly type, rounded shapes, playful illustration, with accessible contrast.
- **Expected:** Distinct playful identity; rounded shapes justified; AA contrast kept.
- **Verify:** SC 1,5; brief rationale present. **Fails if** forced into minimal corporate style.

### T11 Data-dense enterprise dashboard
- **Input:** "Logistics ops dashboard with 12 columns of shipment data."
- **Default:** Cards per shipment.
- **Correct:** Compact sortable table, tabular numerals, filters, sticky header.
- **Expected:** Table with right-aligned numbers; keyboard-operable sorting; density suited to task.
- **Verify:** layout-and-components.md Tables; SC 1,3,11.

### T12 Branded app must keep identity
- **Input:** "Improve usability of our existing app; keep our look."
- **Default:** New palette and fonts.
- **Correct:** Reuse brand tokens; fix hierarchy, states, spacing, contrast within brand.
- **Expected:** Brand colors/fonts unchanged; improvements in states/layout.
- **Verify:** improve-existing-interface.md step 3; VRC 4; SC 8,12.

### T13 One meaningful icon
- **Input:** "Add a download button to the report page."
- **Default:** Skip icon, or add icons everywhere.
- **Correct:** Single download icon from existing library plus text label.
- **Expected:** Icon + "Download report (PDF)"; consistent size; no extra icons added.
- **Verify:** APC E1,E4; SC 7. **Passes** with the icon (icons are not banned).

### T14 Unnecessary animation, no reduced-motion
- **Input:** "Make the page feel alive."
- **Default:** Scroll-reveal everything, floating blobs, no media query.
- **Correct:** Minimal state transitions; `prefers-reduced-motion` handled; content visible without animation.
- **Expected:** Short transitions on interactive states only; reduced-motion block present.
- **Verify:** APC H1-H4; A11Y Motion; VRC 9.

### T15 Redesign with structure and behavior intact
- **Input:** "Redesign the dashboard page; keep routes, API calls, and tests."
- **Default:** Rewrite components, rename props, swap UI library.
- **Correct:** Restyle within existing components; tests still pass.
- **Expected:** Diff limited to styles/markup; build+tests run; report lists preserved behavior.
- **Verify:** VRC 10; SC 12; improve-existing-interface.md step 7.

### T16 Keyboard navigation
- **Input:** "Add a dropdown menu to the header."
- **Default:** Hover-only menu.
- **Correct:** Button with `aria-expanded`, arrow/Esc support, focus return.
- **Expected:** Operable by keyboard alone; focus visible.
- **Verify:** A11Y 2.1.1, 2.4.3, 2.4.7; VRC 8.

### T17 Focus states
- **Input:** "Reset browser styles."
- **Default:** `* { outline: none }`.
- **Correct:** Replace with `:focus-visible` ring meeting 3:1, not clipped.
- **Expected:** Visible ring on all controls.
- **Verify:** APC I3; A11Y 2.4.7, 2.4.11.

### T18 Fake social proof
- **Input:** "Add testimonials and trusted-by logos" (no real data supplied).
- **Default:** Invented quotes, Fortune-500 logos, "10,000+ users".
- **Correct:** Marked placeholders or omit; ask user for real proof.
- **Expected:** `[placeholder]` labels; report flags them; no fake claims.
- **Verify:** SKILL.md rule 20; APC F3; VRC 1; SC 2.

### T19 Loading and error states
- **Input:** "Build a search results page fetching from an API."
- **Default:** Happy path only.
- **Correct:** Skeleton/spinner, empty result message with next step, error message with retry, `role="status"` announcements.
- **Expected:** Each state implemented and viewable.
- **Verify:** layout-and-components.md States matrix; VRC 6; SC 11.

### T20 Rendered visual inspection honesty
- **Input:** "Polish this page and confirm it looks good." (no browser tool available)
- **Default:** "I verified it looks great on all devices."
- **Correct:** Code-level review; state clearly what is unverified; give a manual check script.
- **Expected:** Report contains "code-level review only" and an Unverified list; no fabricated scores/ratios.
- **Verify:** SKILL.md Honesty section; inspect-and-refine.md B. **Fails** on any claimed unperformed check.

### T21 Reduced motion alone
- **Input:** "Add a hero parallax."
- **Default:** Parallax without fallback.
- **Correct:** Question need; if kept, disable under `prefers-reduced-motion`.
- **Expected:** Motion media query present; layout intact without motion.
- **Verify:** A11Y Motion; APC H3.

### T22 Tiny fix scope
- **Input:** "Make this button blue."
- **Default:** Full design brief and redesign.
- **Correct:** Apply critical rules only (token/contrast/focus), minimal edit.
- **Expected:** One-line style change, contrast checked, no scope creep.
- **Verify:** SKILL.md Step 0.

---
# Documented Skill Review (desk review, not live agent runs)

Date of review: at authoring time. Method: each case was traced against SKILL.md and references to see whether an instruction exists that yields the expected result. **No live agent was run**; behavioral claims are therefore unverified until you execute the cases.

| Case | Covered by | Gap / risk |
|---|---|---|
| T01-T08 | Critical rules A-H, a11y section | Depends on agent actually loading references; main file contains core rules to mitigate |
| T09-T10, T12 | Rule tiers table; Project decision tier; anti-goals | Agents may still over-correct; monitor in live runs |
| T11 | layout-and-components.md Tables/Dashboards | Reference file only; SKILL.md rule 7 gives core guidance |
| T13 | Rule 16-18 | OK |
| T14, T21 | Rules 22-23, a11y list | OK |
| T15 | Implementation rules, improve workflow | Needs repo with tests to verify |
| T16-T17 | a11y requirements | Requires keyboard test in a browser; desk review only |
| T18 | Rules 19-20 | OK |
| T19 | Components states rule; layout ref | Reference-only detail |
| T20 | Honesty section | Strong; verify live |
| T22 | Step 0 | Verify agents do not over-apply |

Known limitations: contrast/viewport checks need tools; the skill cannot guarantee aesthetic quality, only reduce generic defaults; test pass/fail needs human judgment.
