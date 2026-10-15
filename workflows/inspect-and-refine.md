# Workflow: Inspect and Refine

Run after any substantial UI change. Repeat until the top issues are fixed.

## A. If a browser/screenshot tool is available
1. Start the dev server (or build + preview). Note the URL.
2. Capture full-page screenshots at desktop (~1440x900) and mobile (~390x844). Add tablet (~768) and narrow (320) for layout-heavy work.
3. Inspect: hierarchy, whitespace, alignment, type, color, rhythm, consistency.
4. Check programmatically for overflow:
   `document.documentElement.scrollWidth > document.documentElement.clientWidth`
5. Exercise states: hover, keyboard focus (Tab through), active, disabled, loading, error, empty.
6. Run automated a11y: axe-core / Lighthouse / Playwright + axe. Record violations.
7. Compute contrast for text and control pairs (script in `references/typography-and-color.md`).
8. Fix top issues in triage order; recapture; compare.

Example Playwright (adapt to the project; requires Playwright installed):
```js
import { test } from '@playwright/test';
for (const [name, w, h] of [['desktop',1440,900],['mobile',390,844]]) {
  test(`shot ${name}`, async ({ page }) => {
    await page.setViewportSize({ width: w, height: h });
    await page.goto('http://localhost:3000/');
    await page.screenshot({ path: `shots/${name}.png`, fullPage: true });
    const overflow = await page.evaluate(() => document.documentElement.scrollWidth > document.documentElement.clientWidth);
    console.log(name, 'horizontal overflow:', overflow);
  });
}
```

## B. If no rendering tools are available
- Do a **code-level review only**: semantics, tokens, contrast math, CSS logic (min-width, overflow, wrapping), state coverage, focus styles, reduced-motion block, breakpoints.
- Run what you can: build, lint, type-check, tests, static a11y lint.
- In the report, write "Code-level review only; not visually verified" and list unverified items (rendering, real breakpoints, screen-reader behavior).
- Optionally give the user a short manual test script (viewports to try, Tab-through, zoom 200%).

## C. Exit criteria
- No broken functionality; no known a11y/readability failures.
- Critical categories >= 4 on the scorecard (or documented exception).
- Report states exactly what was and was not verified.
