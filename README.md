# Skills

Public Codex skills maintained by Willis.

Each branch in this repository is a standalone skill package. Open the branch for the skill you need, then use the folder in that branch as the installable skill source.

## How To Use

1. Choose a skill from the table below.
2. Open its branch.
3. Review the branch README and `manifest.json`.
4. Copy or install the skill folder into your Codex skills directory.

The `main` branch is only the catalog. Skill source files live in the individual branches.

## Skill Catalog

| Skill | Branch | Version | Revision history | What it helps with | Use it when |
| --- | --- | --- | --- | --- | --- |
| Deeply Reader | [`Deeply-Reader-Skill`](https://github.com/Willis1214/Skills/tree/Deeply-Reader-Skill) | `1.0.0` | `v1.0.0`, 2026-07-01: initial central release with evidence-grounded deep reading contracts for long book-like files. | Creates evidence-aware deep reading reports from book-like PDF, DOCX, EPUB, Markdown, and TXT files. | You need more than a shallow summary and want cognitive maps, method extraction, actionable notes, and evidence-aware reading intelligence. |
| Intelligence Forge | [`Intelligence-Forge-Skill`](https://github.com/Willis1214/Skills/tree/Intelligence-Forge-Skill) | `1.0.0` | `v1.0.0`, 2026-06-11: initial public release with Stage 0 domain onboarding, evidence-backed claim validation, promotion gates, stratified sampling, overlays, and `Cannot infer` boundaries. | Forges reusable `domain_intelligence.md` files from many same-domain professional files while preserving evidence, exceptions, project/subtype overlays, user feedback, and extraction limits. | You need to turn scattered domain files, runsets, specs, reports, logs, or historical cases into evidence-backed AI domain constraints without false generalization. |
| Skill Researcher | [`Skill-Researcher-Skill`](https://github.com/Willis1214/Skills/tree/Skill-Researcher-Skill) | `1.1.0` | `v1.1.0`, 2026-05-19: fixed YAML-safe frontmatter, made `$skill-researcher` globally visible, and preserved the Chinese research gate. | Researches local and public skill precedents before creating, updating, installing, or publishing Codex skills. | You need a research-first gate before skill file edits, third-party skill installation, or skill publishing. |
| Skill Cleaner | [`Skill-Cleaner-Skill`](https://github.com/Willis1214/Skills/tree/Skill-Cleaner-Skill) | `1.0.0` | `v1.0.0`, 2026-06-24: initial central release with local skill-root audit, prompt-budget pressure review, duplicate detection, unused-skill candidates, and Chinese-first read-only cleanup recommendations. | Audits local Codex/OpenClaw skill roots, description budget pressure, duplicate skills, and possible unused skills before any cleanup action. | You need a read-only Chinese audit before trimming skill prompt budget, compacting descriptions, or deciding which local skill copies may need cleanup. |
| Issue Analyse | [`Issue-Analyse-Skill`](https://github.com/Willis1214/Skills/tree/Issue-Analyse-Skill) | `1.3.0` | `v1.3.0`, 2026-05-30: realigned the workflow for customer issue support, moved POR/SOP/Email/QC/Policy evidence review before delivery-issue judgment, and added `对外解决方案` plus `双赢路径`. | Helps support customer or stakeholder issues while preserving evidence-backed responsibility boundaries, checking contracts and proof, selecting a support strategy, and preparing safe Chinese external-facing wording. | You need to provide customer support for complaints, upstream/downstream handoffs, release mismatch, mature-system alarms, or corner-case deadlocks without accepting unsupported responsibility. |
| HTML Creator | [`HTML-Creator-Skill`](https://github.com/Willis1214/Skills/tree/HTML-Creator-Skill) | `1.1.0` | `v1.1.0`, 2026-05-19: added diagram routing for flows, state transitions, architecture maps, data movement, and Mermaid/SVG handling. | Creates standalone decision-ready HTML pages with evidence tiers, risks, next actions, and diagram support when structure matters. | Markdown is too flat for a decision page, visual PRD, evidence report, status review, or workflow/architecture explanation. |
| Code Reviewer | [`Code-Reviewer-Skill`](https://github.com/Willis1214/Skills/tree/Code-Reviewer-Skill) | `1.0.0` | Initial public release, 2026-05-18. | Performs static-text release review for source code, diffs, version comparisons, and Codex skill files with risk levels, scoring, contract stability, engineering quality, and release decision. | You need a code release review without running local tools, tests, linters, interpreters, or environment probes. |
| Code-QC-UAT | [`Code-QC-UAT-Skill`](https://github.com/Willis1214/Skills/tree/Code-QC-UAT-Skill) | `1.1.0` | `v1.1.0`, 2026-05-18: renamed to `code-qc-uat`, refocused on executable code functional QC/UAT, and simplified the final report path to `qc_uat/qc_uat_result.md`. | Runs executable QC/UAT for Python, Perl, Tcl, Shell, CLI tools, parsers, converters, and data processors using functional, boundary, and regression cases with evidence-backed gates. | You need to generate `qc_uat/` test artifacts, execute the real target program, and issue a strict `Pass`, `Fail`, or `Reject` release decision. |
| Red Team | [`Red-Team-Skill`](https://github.com/Willis1214/Skills/tree/Red-Team-Skill) | `1.0.0` | Initial public release, 2026-05-18. | Strict adversarial review for plans, prompts, workflows, PRDs, proposals, and decision material. | You need risks, hidden assumptions, boundary cases, logic gaps, or execution weaknesses surfaced before moving forward. |
| Brainstorm | [`Brainstorm-Skill`](https://github.com/Willis1214/Skills/tree/Brainstorm-Skill) | `2.2.0` | `v2.2.0`, 2026-07-09: clarified Boundary Officer, Attacker, Reflector, and Red Team final-gate responsibilities, plus blocking vs residual `TBD` handling. | Clarifies ambiguous engineering or product ideas through repeatable role-based rounds that define boundaries, attack boundary risks, expose map-changing unknowns, and then produce PRD Markdown, user-story-map HTML, and QC checklist Markdown after Red Team and optional Front Taste gates. | You need a confirmed requirement package before implementation and want every discussion round to separate boundary definition, risk attack, critical reflection, QC thinking, and final gate decisions without prescribing the implementation path. |
| Diff Output | [`Diff-Output-Skill`](https://github.com/Willis1214/Skills/tree/Diff-Output-Skill) | `1.0.0` | Initial public release, 2026-05-18. | A fixed comparison table for changes, before/after states, version differences, and update summaries. | You want a concise table showing `Type`, `Content`, `As is`, `To be`, and `Why`. |
| Wechat Message | [`Wechat-Message-Skill`](https://github.com/Willis1214/Skills/tree/Wechat-Message-Skill) | `1.0.0` | Initial public release. | Sends a WeChat message through the visible macOS desktop WeChat app using a controlled keyboard workflow. | You need Codex to send a message to a named WeChat contact or group without private WeChat APIs or bridge services. |
| Token Gate | [`Token-Gate-Skill`](https://github.com/Willis1214/Skills/tree/Token-Gate-Skill) | `0.1.0` | Initial public release candidate, 2026-05-05. | Prevents avoidable high-token work before large scans, long logs, large documents, generated artifacts, OCR, or subagent-heavy tasks. | A task may consume a lot of context and a cheaper path can preserve the same final result. |
| Memory Governor | [`Memory-Governor-Skill`](https://github.com/Willis1214/Skills/tree/Memory-Governor-Skill) | `0.1.0` | Initial public release, 2026-05-18. | Governs long-term command memory by detecting reusable user rules, asking for approval, and writing approved entries to memory. | A user wants durable preferences, prohibitions, shortcuts, or workflow rules remembered across future Codex tasks. |

## Repository Layout

- `main`: catalog and usage overview.
- One branch per skill package.
- Branch names match the original public skill package names.

## Maintenance

When a skill changes, update its branch first, then update this catalog so readers can see the current version, revision history, purpose, and trigger conditions from `main`.
