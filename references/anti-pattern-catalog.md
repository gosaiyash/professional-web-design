# Anti-Pattern Catalog

Contents: How to use | A Layout | B Effects | C Rounding/containers | D Typography | E Icons/emoji | F Copy | G Imagery | H Motion | I Interaction/forms | J Dashboards

**How to use.** Each entry: *Detect* what you see, *Why* it weakens the design, *When fine* the legitimate case, *Fix*. These are review triggers. A flagged pattern passes if you can state a project-specific reason. Never claim a design "looks AI-made"; describe the observable problem.

## A. Generic layouts
**A1. Centered headline + CTA + gradient + three identical feature cards**
- Why: could describe any product; no hierarchy among features.
- When fine: genuinely three equal-weight, similar-length items; or a deliberately simple launch page.
- Fix: lead with the product's concrete job and a real view of it; rank features by importance; use list, table, or one featured item plus supporting items.
**A2. Every section has the same structure** (centered heading, subtitle, grid). Fix: let content choose the form (timeline, comparison, split, quote, table).
**A3. Equal grids for unequal content.** Fix: size by priority.
**A4. Over-centering.** Fix: left-align scannable text; center only short, ceremonial content.
**A5. Card overuse.** Fix: whitespace, dividers, typography; cards only for independent items/interactions.
**A6. Huge empty hero, little content.** Fix: reduce height; add the substance (proof, product view, key facts).
**A7. Interchangeable headline.** Test: swap in a competitor's name; if it still works, rewrite.

## B. Excessive visual effects
**B1. Purple-to-blue gradients without brand reason.** When fine: it is the brand. Fix: use brand color; flat or subtle tonal fills.
**B2. Glow, neon outlines, blobs, particles, meaningless geometry.** Fix: remove or replace with real content.
**B3. Default glassmorphism/backdrop blur.** When fine: overlays where seeing context behind matters, if contrast holds. Fix: solid surface.
**B4. Big soft shadows everywhere.** Fix: one elevation scale used by role (popover > card > flat); prefer borders for static grouping.
**B5. Stacked effects (gradient + shadow + glow + border).** Fix: pick one.
**B6. Effects that hurt contrast/readability.** Always fix.

## C. Rounding and containers
**C1. Everything in a rounded card; nested cards.** Fix: flatten; align; use separators.
**C2. Pills for everything.** Fix: radius by component role.
**C3. Thick borders + shadows with no grouping meaning.** Fix: remove one or both.
**C4. Arbitrary radius mix (6, 10, 14, 20, 24 on one page).** Fix: 2-3 radius tokens.

## D. Typography
**D1. Unconsidered default fonts.** Fix: choose and justify; fine if the choice is deliberate.
**D2. Oversized headings with no hierarchy role.** Fix: size by information level.
**D3. ALL-CAPS micro-labels everywhere.** Fix: use sparingly for true metadata; add tracking when used.
**D4. Too many families/weights.** Fix: 1-2 families, 3-4 weights max typically.
**D5. Tight leading, over-long lines, faint body text.** Fix: 1.5-1.7 line-height, 45-80ch, pass contrast.
**D6. Headings wrapping/colliding on mobile.** Fix: fluid type with `clamp()`, `text-wrap: balance`, test at 320-390px.
**D7. Vague superlative copy.** See F.

## E. Icons and emoji
**E1. Icon beside every heading/feature.** Fix: keep icons that carry meaning (action, state, category).
**E2. Emoji as UI icons.** Fix: icon set or text.
**E3. Mixed icon styles/libraries.** Fix: one library, one size/stroke.
**E4. Icon-only controls without names.** Fix: `aria-label`.
**E5. Icon dependency added for decoration.** Fix: reuse existing or use text.

## F. Generic marketing content
**F1. Unsubstantiated superlatives** ("revolutionary", "next-gen"). Fix: state the concrete outcome or capability.
**F2. Repeated vague CTAs.** Fix: verb + object ("Start free trial", "View pricing", "Book a demo").
**F3. Placeholder testimonials/logos/stats presented as real.** Fix: remove, or mark `[placeholder]`; never ship as fact.
**F4. Filler text.** Fix: cut the section.

## G. Generic imagery
**G1. Stock-style unrelated illustration.** **G2. Fake screenshots.** **G3. Floating blobs/abstract shapes as default hero.** **G4. Generated images with fake UI text.**
Fix: real assets, authentic screenshots, relevant photos, purposeful illustration, or type-led composition. Never imply a fabricated asset is a real customer/product/result.

## H. Gratuitous animation
**H1. Scroll-reveal on every section. H2. Bounce/elastic/floating. H3. Parallax by default. H4. Motion delaying content or interfering with forms.**
Fix: transitions of 120-250ms on state changes; honor `prefers-reduced-motion`; content visible without JS animation.

## I. Interaction and forms
**I1. Placeholder-only labels.** Fix: persistent visible labels.
**I2. Non-interactive element styled like a button/link.** Fix: restyle, or make it real.
**I3. Missing focus styles / `outline: none`.** Fix: `:focus-visible` ring >= 3:1 contrast.
**I4. Missing loading/empty/error/success states.** Fix: design each.
**I5. Dead links/buttons ("#" hrefs, no-op handlers).** Fix: wire up or remove; disclose.

## J. Dashboards
**J1. Random KPI cards with invented numbers.** Fix: real data or clearly labeled sample data; task-led hierarchy.
**J2. Charts for decoration.** Fix: each chart answers a named question; label axes and units.
**J3. Cards where a table fits.** Fix: compact, sortable, aligned numeric columns.
