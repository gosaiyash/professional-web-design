# Visual Review Checklist

Use on every relevant project. Mark each: Pass / Fail / N/A / Unverified. Never mark Pass for something you did not inspect.

## 0. Setup
- [ ] Mode of review recorded: rendered (tool + viewports) or code-only
- [ ] Brief exists and matches what was built

## 1. Purpose & content
- [ ] Primary action obvious within 5 seconds
- [ ] Headline and copy specific to this product (competitor-swap test)
- [ ] No invented testimonials, logos, stats, screenshots, features
- [ ] Placeholders are marked and listed in the report
- [ ] Every section earns its place

## 2. Hierarchy & composition
- [ ] Squint test: top 2 elements identifiable
- [ ] Max ~3 emphasis levels per view
- [ ] Sections vary by content need, not copy-pasted structure
- [ ] Alignment to a small set of edges; consistent gutters
- [ ] Containers only where grouping needs them

## 3. Typography
- [ ] Defined roles; limited families/sizes
- [ ] Body 16px+, leading ~1.5-1.7, measure 45-80ch
- [ ] No awkward wraps/collisions at 320-390px
- [ ] Caps/micro-labels used sparingly

## 4. Color & tokens
- [ ] One deliberate accent; neutrals; semantic states
- [ ] Contrast computed for text pairs (4.5:1 / 3:1 large)
- [ ] Non-text contrast (borders, focus ring, icons) >= 3:1
- [ ] Status never by color alone
- [ ] Values come from tokens, not scattered hex

## 5. Decoration restraint
- [ ] Each gradient/shadow/blur/glow has a stated purpose
- [ ] No stacked effects; radius from the scale
- [ ] Icons: one set, meaningful, consistent, named when icon-only
- [ ] No emoji as UI icons

## 6. Components & states
- [ ] Hover, focus, active, disabled, loading, error, empty, success covered where applicable
- [ ] Forms: persistent labels, associated errors, correct input types
- [ ] Nothing non-interactive looks clickable; no dead controls/links

## 7. Responsive
- [ ] Checked mobile, tablet, desktop (list widths)
- [ ] No horizontal page overflow; tables handled
- [ ] Nav works on narrow screens; targets adequate
- [ ] 200% zoom and 320px reflow OK

## 8. Accessibility
- [ ] Keyboard-only pass; focus visible and not obscured
- [ ] Semantic landmarks, heading order, labels
- [ ] Reduced motion honored
- [ ] Automated check run (name tool) / or marked Unverified

## 9. Motion
- [ ] Animation communicates state; short; non-blocking
- [ ] Content visible without animation

## 10. Technical
- [ ] Reused existing stack/components/tokens; no needless dependencies
- [ ] Routes and behavior preserved; build/lint/tests run
- [ ] No console errors; images sized; fonts limited

## Triage order
Broken function > accessibility/readability > layout/responsive > hierarchy/content > system consistency > decoration > polish.
