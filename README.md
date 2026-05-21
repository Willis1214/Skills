# Issue Analyse Skill

`issue-analyse` helps discuss disputed issues without jumping directly to blame.

It follows a Chinese-first workflow:

1. 先还原现场: known facts, timeline, missing Evidence, and provisional hypotheses.
2. 再判断是否构成 issue: expected behavior, actual behavior, and material impact.
3. 再审合同和证据: PRD, SOP, API contract, handoff agreement, release checklist, waiver, and Evidence strength.
4. 最后做归因和沟通: attribution matrix, Owner / RACI, Confidence, and Chinese communication boundaries.

## When To Use

Use this skill when you need to:

- restore what happened before deciding whether an issue exists;
- analyze whether a customer complaint, upstream input, release mismatch, legacy behavior, or owner handoff is actually a defect;
- separate `Self`, `Other Owner`, `Upstream Dependency`, `Process / Contract Gap`, `Requester / Scope Drift`, and `Evidence Gap`;
- prepare safe Chinese wording for sensitive responsibility discussions.

## Output Style

Default output labels are Chinese. Technical terms such as `Evidence`, `Owner`, `RACI`, `Confidence`, `baseline`, `waiver`, `special handle`, and `release gate` are preserved when useful.

Complex communication output uses:

- `可说`
- `不应说`
- `还需补 Evidence`
- `稳妥表达`

## Version

Current version: `1.0.0`

Revision history summary:

- `1.0.0`: Initial central `Skills` publication. Adds the reconstruction-first workflow, Chinese-first output templates, and investigation methods for legacy issues, baseline drift, complaint validity, waiver / special handle search, change control, RACI handoff, and fix-owner versus root-cause-owner separation.
