# Design Pro (`design-pro`)

> **Professional Web Design & Anti-AI-Slop for AI Coding Assistants**  
> A structured, engineering-first skill that empowers AI coding agents (Google Antigravity, Claude Code, Cursor, Copilot, etc.) to design websites and web applications like thoughtful senior frontend design engineers.

---

## ⚡ Quick Summary / Short Description

**`design-pro`** enforces a purpose-first design discipline on AI coding agents. Instead of producing cookie-cutter, generic "AI slop" (random gradient soup, purposeless floating cards, non-accessible contrasts, unstyled buttons, and filler copy), it mandates:

- **Purpose Before Decoration**: Specific layout concepts tailored to product goals and target audience.
- **Accessible by Default**: Strict adherence to WCAG 2.2 AA (4.5:1 / 3:1 contrast, keyboard focus, 24x24px click targets, proper semantic HTML).
- **Deliberate Design Tokens**: Systematic scales for spacing, typography, radii, and semantic color palettes.
- **Real Content & Hierarchy**: No placeholder testimonials or fabricated metrics; structured typographic rhythm and scannability.
- **Verification & Review Loop**: Honest validation across mobile, tablet, and desktop viewports with a 12-category quality scorecard.

---

## 📁 Repository Structure

```text
design-pro/
├── SKILL.md              # Main entry point: core rules, principles, and execution workflow
├── README.md             # Overview, installation guides, and documentation
├── workflows/            # Task-specific procedural runbooks
│   ├── design-from-scratch.md         # Building a new interface from scratch
│   ├── improve-existing-interface.md  # Auditing and polishing an existing interface
│   └── inspect-and-refine.md          # Visual verification and inspection loops
├── references/           # In-depth design guides loaded on demand
│   ├── visual-design-principles.md    # Hierarchy, composition, spacing, and rhythm
│   ├── anti-pattern-catalog.md        # AI slop patterns, detection, and remediation
│   ├── typography-and-color.md        # Type scales, palettes, tokens, and contrast
│   ├── layout-and-components.md       # Grids, forms, tables, dashboards, and states
│   ├── accessibility-and-responsive-design.md # WCAG 2.2 AA and responsive checks
│   └── visual-review-checklist.md     # Per-project visual quality checklist
└── tests/                # Evaluation & benchmarking
    ├── quality-scorecard.md           # 12-category scoring framework (0-5 scale)
    └── test-cases.md                  # 22 diverse UI test and evaluation scenarios
```

---

## 🚀 Installation & Setup

### 1. Google Antigravity IDE
To install globally across all projects on your machine:
```bash
# Windows (PowerShell)
Copy-Item -Recurse -Force . "C:\Users\<YourUser>\.gemini\config\skills\design-pro"

# macOS / Linux
cp -r . ~/.gemini/config/skills/design-pro
```
Alternatively, for project-level scope, place it in `.agents/skills/design-pro` inside your workspace root.

### 2. Claude Code
- **Global**: Copy the directory into `~/.claude/skills/design-pro/`
- **Project-level**: Copy into `<repo-root>/.claude/skills/design-pro/`

### 3. Cursor / Windsurf / GitHub Copilot / Gemini CLI
Add a reference in your project's rule file (`.cursor/rules`, `AGENTS.md`, `CLAUDE.md`, or `GEMINI.md`):
> *For any frontend, UI/UX, or web design work, refer to and follow `SKILL.md`.*

---

## 🎯 When It Triggers

The skill activates whenever the agent is tasked to:
- Build, design, redesign, modernize, or audit web pages, dashboards, landing pages, or components.
- Fix UI aesthetics, layout bugs, responsive wrapping issues, or contrast issues.
- Remove generic "AI-looking" styles and replace them with distinct, brand-aligned aesthetics.

---

## 📋 The 8-Phase Execution Workflow

1. **Inspect**: Understand product goals, target audience, stack, and constraints.
2. **Diagnose**: Identify specific defects, accessibility bottlenecks, and visual dissonance.
3. **Plan**: Formulate a concise 10–20 line design brief before writing code.
4. **Implement**: Code using semantic HTML, deliberate tokens, and robust component states.
5. **Inspect the Result**: Test rendered views on desktop (~1440px) and mobile (~390px).
6. **Refine**: Address priority defects in function, accessibility, and hierarchy.
7. **Verify**: Check WCAG 2.2 AA standards, keyboard navigation, and reflow at 320px.
8. **Report**: Deliver an honest summary with scorecard ratings and verified states.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
