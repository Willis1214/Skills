---
name: html-creator
description: Create or revise standalone decision-ready HTML pages from requirements, Markdown drafts, research notes, reports, comparisons, PRDs, code-review findings, market briefs, project updates, or evidence-heavy material. Use when the user asks for HTML output, a high-density visual report, decision page, interactive artifact, visual PRD, readable local HTML, or when Markdown would be too linear for comparing options, risks, evidence levels, timelines, flows, diagrams, system architecture, state transitions, or next actions. Do not use for production web-app implementation, generic landing pages, Figma/PPT work, simple short notes, or source documents that should remain Markdown-first.
---

# HTML Creator

Create self-contained HTML pages that help a human decide faster. Treat HTML as the presentation and decision layer; keep Markdown, JSON, CSV, or source files as the editable evidence layer when they already exist.

## Fit Gate

Use HTML when at least one is true:

- The material is multi-dimensional: options, trade-offs, evidence tiers, risks, timelines, owners, or next actions.
- The reader needs to scan first and drill down later.
- The output benefits from visual hierarchy, tables, tabs, filters, collapsible sections, timelines, matrices, or anchored navigation.
- The output needs a workflow, state transition, system architecture, dependency map, data flow, or screen journey that prose and tables would flatten.
- The user needs a browser-openable artifact for review, archiving, briefing, or decision meetings.
- A Markdown draft has become too long, flat, or hard to compare.

Prefer Markdown when:

- The content is short, linear, or still being heavily edited.
- Git diff, copy editing, or prompt reuse matters more than presentation.
- The user asks for a README, source spec, prompt, plain memo, or minimal text output.
- HTML styling or interactivity would add no decision value.

Do not take over production frontend tasks. If the user asks to modify an existing app, build a real website, implement React/Next.js UI, or match a design system in code, use the appropriate frontend/design workflow instead.

## Output Contract

- Produce a real `.html` file, not a chat-only snippet, unless the user explicitly asks for inline code.
- Default to one self-contained file with inline CSS and only minimal inline JavaScript when it improves navigation, filtering, toggles, sorting, or drill-down.
- Diagrams must remain inspectable. Prefer inline SVG/CSS diagrams or pre-rendered Mermaid SVG with the source diagram text preserved in a `<details>` block or HTML comment.
- Respect the active workspace rules. If no stronger project rule exists, write final HTML under `output/`.
- Do not create scattered root artifacts. Use `temp/` for temporary checks and `output/` for final deliverables when project rules require it.
- Preserve the source-of-truth boundary: do not invent evidence, metrics, decisions, citations, or claims. Mark assumptions and unknowns explicitly.
- If live facts, current market data, law, product availability, or "latest" information affects the page, verify with live sources before generating claims.

## Page Archetypes

Choose exactly one primary archetype, then adapt lightly.

### Decision Brief

Use for: technical choices, investment/research calls, vendor comparison, project direction.

Sections:
- Decision question
- Recommendation with confidence
- Option comparison table
- Decision criteria and weights when useful
- Evidence by strength: retained, downgraded, eliminated
- Risk matrix
- What would change the decision
- Next actions and owners

### Requirements / Visual PRD

Use for: PRD, feature scope, requirement updates, stakeholder review.

Sections:
- Product objective
- Target users and jobs
- Scope and non-goals
- User flow or journey
- Functional requirements
- Non-functional requirements
- Acceptance criteria
- Open questions
- Change log or feedback queue when revising

### Research / Evidence Report

Use for: web research, market analysis, literature/source synthesis, due diligence.

Sections:
- Executive conclusion
- Source quality map
- Key findings grouped by theme
- Evidence table with source, date, confidence, and implication
- Contradictions and weak signals
- Retained / downgraded / eliminated conclusions
- Decision implications

### Status / Daily Report

Use for: project status, daily report, incident update, work summary.

Sections:
- Current state
- Completed / in progress / blocked
- Timeline
- Metrics or artifacts
- Risks and blockers
- Decisions made
- Next checkpoint

### Review / Risk Page

Use for: code review summary, launch review, QC/UAT, release decision.

Sections:
- Release decision
- Severity summary
- Findings by risk level
- Contract stability
- Test coverage and gaps
- Required fixes before approval
- Residual risk

Read `references/html_creator_patterns.md` when building a real page and you need layout details, component choices, or validation prompts.
Read `references/diagram_patterns.md` when the page needs flowcharts, state diagrams, sequence diagrams, architecture maps, data lineage, screen transitions, or other node-edge visualizations.

## Diagram Layer

Use a diagram when it changes the reader's understanding faster than a paragraph or table.

Default routing:

- Process, decision, workflow, or screen journey: flowchart.
- API calls, agent/tool handoffs, or approval loops: sequence diagram.
- Lifecycle, status, retry, or release gates: state diagram.
- System architecture, ownership, dependencies, or data movement: grouped flowchart or architecture map.
- Data model or schema relationships: ER or class-style diagram.

Keep diagrams purposeful:

- One main idea per diagram.
- Stable node labels; avoid decorative labels and vague names.
- Solid lines for primary flow; dashed lines for dependency, reference, influence, or optional paths.
- Put line labels close to edges and avoid arrows pointing into node centers when drawing custom SVG.
- Pair every central diagram with a short "why this matters" or "decision implication" note.

Do not add a diagram just to decorate the page. If a simple table is clearer, use the table.

## Style Rules

The default style is dense, calm, and decision-oriented:

- Prefer restrained editorial/report layouts over marketing pages.
- Use clear typographic hierarchy, compact spacing, and strong tables.
- Keep cards only for repeated items, metric tiles, or framed tools. Do not put cards inside cards.
- Use 8px or smaller border radius unless the existing design system requires otherwise.
- Use color semantically: risk, confidence, status, category, evidence strength. Do not make a one-hue decorative palette.
- Avoid decorative gradients, bokeh, or floating orbs.
- Keep content scannable: sticky or anchored table of contents for long pages, summary first, details after.
- Use `<details>` for secondary evidence and appendices when it reduces clutter.
- Use tabs, filters, or sorting only when the page has enough data to justify the interaction.
- Make mobile readable: responsive grids, no horizontal-only decision content without a fallback, no overlapping text.
- Include print-friendly basics when the artifact is likely to be archived or shared.

## Content Rules

Before writing HTML, build a compact content model:

- Facts: directly supported by supplied or verified evidence.
- Interpretations: analysis drawn from facts.
- Assumptions: unverified but necessary working assumptions.
- Decisions: selected direction and rationale.
- Open questions: items not yet resolved.
- Actions: owner, next step, due date if known.

Keep these categories visually distinct. Do not mix retained, downgraded, and eliminated evidence in one undifferentiated flow.

For decision pages, show "why this matters" and "what to do next"; do not merely beautify the source text.

## Build Workflow

1. Confirm fit and source material.
   - If HTML is not justified, say Markdown is the better source format and explain briefly.
   - If HTML is justified, state the chosen archetype.

2. Normalize the information.
   - Extract the decision question, audience, source facts, assumptions, unresolved questions, and desired outcome.
   - Keep source references and dates attached to claims.

3. Design the information architecture.
   - Put executive summary at the top.
   - Place comparisons, matrices, evidence, and risks where the reader can scan them without reading prose first.
   - Route workflows, state transitions, architecture, and data movement through the Diagram Layer when they are central to the decision.
   - Move detail-heavy material into expandable sections or appendix.

4. Implement the HTML.
   - Use semantic HTML: `header`, `main`, `section`, `nav`, `table`, `details`, `footer`.
   - Use CSS variables for palette, spacing, typography, and status colors.
   - Keep JavaScript optional and small. Do not add frameworks unless the user explicitly asks or the artifact requires complex interaction.
   - Prefer offline-safe output. Avoid external fonts, CDNs, images, and scripts unless explicitly approved.
   - For diagrams, default to inline SVG/CSS or locally rendered SVG. Do not depend on CDN Mermaid, D3, or Cytoscape unless the user approves that dependency.

5. Validate.
   - Parse or lint the HTML when practical.
   - Open or render-preview the page when a browser tool is available.
   - Check desktop and mobile widths for text overlap, cramped tables, and broken navigation.
   - If JavaScript exists, check the browser console when possible.
   - If diagrams exist, verify they render, fit mobile width, keep labels readable, and preserve diagram source text when generated from Mermaid or another DSL.
   - Confirm there is no placeholder text, unsupported claim, broken local asset path, or accidental external dependency.

6. Report.
   - Return the final HTML path, overwrite status, validation performed, and any unverified claims or remaining risks.

## Minimal Validation Commands

Use project-native tools first. If none exist, these checks are acceptable:

```bash
python3 - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
path = Path("output/page.html")
class P(HTMLParser): pass
P().feed(path.read_text(encoding="utf-8"))
print(f"HTML parsed: {path}")
PY
```

For browser checks, use the available in-app browser, Playwright, or a local browser preview according to the environment. If `file://` is blocked by the tool, pair parser checks with a local browser preview and state that limitation.

## Negative Triggers

Do not use this skill for:

- A production app page that must be integrated into an existing codebase.
- A generic marketing landing page where the user's goal is brand/site design rather than decision display.
- Pure PowerPoint, Word, PDF, or Figma output.
- A short answer, brief rewrite, or one-screen Markdown note.
- Raw data processing where the main task is extraction, cleaning, or statistical computation.

When a neighboring skill is better, route there and keep HTML Creator out of the way.
