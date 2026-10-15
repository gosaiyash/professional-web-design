# Typography and Color

Contents: Typography roles | Scale | Pairing | Color process | Token set | Contrast math | Example tokens

## Typography roles
| Role | Purpose | Typical treatment |
|---|---|---|
| Display | Hero/landing statement | Large, tight leading (1.05-1.2), `clamp()` sizing |
| Page heading (h1) | One per page | Clear, not necessarily huge |
| Section heading (h2/h3) | Structure | Distinct step down from h1 |
| Body | Reading | 16-18px, leading 1.5-1.7, measure 45-80ch |
| Supporting | Captions, help | 14-15px, must still pass contrast |
| Label/metadata | Form labels, tags | 12-14px, weight 500-600, sparing caps |
| Button/nav | Controls | Consistent weight; sentence case by default |

Use only the families and sizes the content needs. Choose type for brand, language support (check glyph coverage for the user's scripts), density, and performance (limit font files, `font-display: swap`).

## Scale
Pick a ratio (1.125 dense UI, 1.2-1.25 general, 1.333 editorial) or hand-tune. Define as tokens. Make display sizes fluid:
```css
--text-display: clamp(2.25rem, 1.2rem + 4vw, 4.5rem);
```
Add `text-wrap: balance` to headings and `text-wrap: pretty` to paragraphs where supported.

## Pairing
One family is often enough (vary weight/size). If pairing, contrast roles (e.g. serif display + sans body), not two similar sans. Inter/Roboto/system stacks are legitimate when chosen for reasons (UI density, performance, neutrality). Do not treat a trendy pair as design.

## Color process
1. Brand personality, industry, audience, context.
2. Inspect existing logo/brand palette; reuse it.
3. Primary accent only with a credible reason.
4. Neutrals for surfaces/text (tint toward the brand hue slightly for cohesion).
5. Secondary only if needed.
6. Semantic: success, warning, error, info (do not reuse brand accent as error).
7. Validate contrast pairs.
8. Check in real components and every state.
Professional does not equal blue/black/white; playful, luxury, and technical products each justify different palettes.

## Token set (adapt names to the project)
```css
:root {
  /* color */
  --color-brand-primary: ;   --color-brand-primary-hover: ;
  --color-text-primary: ;    --color-text-secondary: ;   --color-text-on-brand: ;
  --color-bg: ;              --color-surface: ;          --color-surface-raised: ;
  --color-border: ;          --color-border-strong: ;    --color-focus-ring: ;
  --color-success: ; --color-warning: ; --color-error: ; --color-info: ;
  /* type */
  --font-body: ; --font-display: ; --font-mono: ;
  --text-xs: ; --text-sm: ; --text-base: ; --text-lg: ; --text-xl: ; --text-2xl: ; --text-display: ;
  --leading-tight: 1.15; --leading-body: 1.6;
  /* space */
  --space-1: .25rem; --space-2: .5rem; --space-3: .75rem; --space-4: 1rem; --space-6: 1.5rem; --space-8: 2rem; --space-12: 3rem; --space-16: 4rem;
  /* shape & depth */
  --radius-sm: ; --radius-md: ; --radius-lg: ; --radius-full: 9999px;
  --shadow-1: ; --shadow-2: ;
  /* layout */
  --content-prose: 65ch; --content-wide: 72rem;
  /* motion */
  --duration-fast: 120ms; --duration-base: 200ms; --ease-standard: cubic-bezier(.2,0,0,1);
}
@media (prefers-reduced-motion: reduce) { :root { --duration-fast: 0ms; --duration-base: 0ms; } }
```
CSS custom properties are cascade-aware: scope overrides (dark theme, component variants) by redefining tokens on a selector rather than duplicating rules (MDN: Using CSS custom properties). The USWDS design-tokens approach is a good model for naming and tiering tokens.
For a tiny page, 6-10 tokens are enough. Do not build a 200-token system for a landing page.

## Contrast math (WCAG relative luminance)
L = 0.2126 R + 0.7152 G + 0.0722 B, with each channel c in [0,1] linearized: c<=0.04045 ? c/12.92 : ((c+0.055)/1.055)^2.4.
Ratio = (L_lighter + 0.05) / (L_darker + 0.05).
Required: text 4.5:1 (3:1 large: >=24px regular or >=18.66px bold); UI components and meaningful graphics 3:1.
Quick script:
```python
def lum(h):
    h=h.lstrip('#'); r,g,b=[int(h[i:i+2],16)/255 for i in (0,2,4)]
    f=lambda c: c/12.92 if c<=0.04045 else ((c+0.055)/1.055)**2.4
    return 0.2126*f(r)+0.7152*f(g)+0.0722*f(b)
def ratio(a,b):
    la,lb=sorted([lum(a),lum(b)],reverse=True); return (la+0.05)/(lb+0.05)
```
Check: body on bg, secondary text on bg and on surface, placeholder, link, button label on brand, disabled-but-informative text, focus ring vs adjacent colors, input borders, chart series against bg.
Do not rely on color alone for status; add text, icon, or pattern.
