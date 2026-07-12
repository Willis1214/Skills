# Semantic Component Catalog

Use components to express meaning, not to decorate empty space. Each component must pass the `use_when`, `avoid_when`, and `fallback` rules before implementation.

## Framing and Narrative

1. `decision-banner` — recommendation, confidence, risk, and next action; avoid for neutral summaries.
2. `lead-block` — title, subtitle, audience, and context; avoid repeating it for every section.
3. `metric-rail` — a small set of stable numeric summaries; avoid for speculative or incomparable values.
4. `status-rail` — current state, owner, severity, or readiness; avoid when status is not actionable.
5. `section-rule` — a light structural break with a clear label; avoid decorative section dividers.

## Comparison and Assessment

6. `comparison-table` — shared criteria across options; always provide a narrow-screen summary.
7. `comparison-rail` — visual before/after or option-to-option contrast; avoid when criteria are unrelated.
8. `scorecard` — explicit dimensions with a stated scoring basis; never imply unsupported precision.
9. `quadrant-matrix` — two defined axes and comparable points; do not use as a generic scatter decoration.
10. `criteria-matrix` — many-to-many mapping between requirements, options, risks, or owners.

## Flow and Time

11. `timeline` — ordered events, milestones, or evidence dates.
12. `stepper` — finite procedure with current/next/completed state.
13. `swimlane` — sequence across owners, systems, or roles.
14. `lifecycle-rail` — allowed states, transitions, retry, or release gates.
15. `journey-map` — user or reader stages with needs, friction, and actions.

## Structure, Relationship, and Data

16. `concentric-hierarchy` — nested layers, scope, or priorities; use only when nesting is real.
17. `relationship-overlap` — explicit set intersection or shared concerns.
18. `pyramid-hierarchy` — ordered levels, maturity, funnel, or argument structure.
19. `architecture-map` — grouped nodes, ownership boundaries, and dependencies.
20. `data-figure` — bar, trend, heatmap, radar, or other chart with labeled data and a text takeaway.

## Evidence and Detail

21. `evidence-strip` — one claim, source/status, and confidence at scan speed.
22. `quote-callout` — a supported key sentence or user-provided quote; never use as filler.
23. `figure-annotation` — image, diagram, or screenshot with labels explaining why it matters.
24. `details-source-note` — secondary evidence, source notes, caveats, or alternate reasoning.
25. `code-terminal-block` — code, command, prompt, or configuration that must preserve exact text.

## Component Contract

For each selected component, record:

- `purpose`: the decision or reading job it serves.
- `use_when`: content conditions that justify it.
- `avoid_when`: semantic or density conditions that disqualify it.
- `required_data`: minimum fields; missing fields become `TBD`, not invented values.
- `visual_anatomy`: title, body, label, edge, axis, legend, or source treatment.
- `semantic_color_roles`: what colors mean and what must remain legible without color.
- `responsive_fallback`: stack, summarize, reflow, or provide a text equivalent.
- `print_fallback`: what remains when controls and interactive affordances disappear.
- `accessibility_notes`: heading order, labels, focus, contrast, and reading order.

## Composition Limits

- Select 2–6 components for a normal page section.
- Do not repeat the same framed component more than three times without a clear grouping reason.
- Do not place a card inside a card unless the inner unit is a genuinely repeated item or tool.
- Prefer one dominant proof object over several decorative mini-graphics.
