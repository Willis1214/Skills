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
| Skill Researcher | [`Skill-Researcher-Skill`](https://github.com/Willis1214/Skills/tree/Skill-Researcher-Skill) | `1.1.0` | `v1.1.0`, 2026-05-19: fixed YAML-safe frontmatter, made `$skill-researcher` globally visible, and preserved the Chinese research gate. | Researches local and public skill precedents before creating, updating, installing, or publishing Codex skills. | You need a research-first gate before skill file edits, third-party skill installation, or skill publishing. |
| Programming Query | [`Programming-Query-Skill`](https://github.com/Willis1214/Skills/tree/Programming-Query-Skill) | `1.0.0` | Initial central release, 2026-05-26. | Finds reusable program assets before coding, checks native-code fit, and identifies reusable modules or gaps for implementation. | You need to query structured program assets, program cards, program intelligence, native source code, or reusable modules before writing new code. |
| Issue Analyse | [`Issue-Analyse-Skill`](https://github.com/Willis1214/Skills/tree/Issue-Analyse-Skill) | `1.1.0` | `v1.1.0`, 2026-05-21: made complaint / feedback challenge the first gate, added past/current/related-project checks, and switched default mixed English fields to Chinese terms such as `结论把握度`, `待补证据`, and `证据链`. | Challenges whether a reported problem is established, reconstructs the scene, checks contract and proof boundaries, and prepares safe Chinese attribution wording. | You need to discuss responsibility, customer complaints, upstream/downstream handoffs, legacy behavior, release mismatch, or scope drift without jumping directly to blame. |
| HTML Creator | [`HTML-Creator-Skill`](https://github.com/Willis1214/Skills/tree/HTML-Creator-Skill) | `1.1.0` | `v1.1.0`, 2026-05-19: added diagram routing for flows, state transitions, architecture maps, data movement, and Mermaid/SVG handling. | Creates standalone decision-ready HTML pages with evidence tiers, risks, next actions, and diagram support when structure matters. | Markdown is too flat for a decision page, visual PRD, evidence report, status review, or workflow/architecture explanation. |
| Code Reviewer | [`Code-Reviewer-Skill`](https://github.com/Willis1214/Skills/tree/Code-Reviewer-Skill) | `1.0.0` | Initial public release, 2026-05-18. | Performs static-text release review for source code, diffs, version comparisons, and Codex skill files with risk levels, scoring, contract stability, engineering quality, and release decision. | You need a code release review without running local tools, tests, linters, interpreters, or environment probes. |
| Code-QC-UAT | [`Code-QC-UAT-Skill`](https://github.com/Willis1214/Skills/tree/Code-QC-UAT-Skill) | `1.1.0` | `v1.1.0`, 2026-05-18: renamed to `code-qc-uat`, refocused on executable code functional QC/UAT, and simplified the final report path to `qc_uat/qc_uat_result.md`. | Runs executable QC/UAT for Python, Perl, Tcl, Shell, CLI tools, parsers, converters, and data processors using functional, boundary, and regression cases with evidence-backed gates. | You need to generate `qc_uat/` test artifacts, execute the real target program, and issue a strict `Pass`, `Fail`, or `Reject` release decision. |
| Red Team | [`Red-Team-Skill`](https://github.com/Willis1214/Skills/tree/Red-Team-Skill) | `1.0.0` | Initial public release, 2026-05-18. | Strict adversarial review for plans, prompts, workflows, PRDs, proposals, and decision material. | You need risks, hidden assumptions, boundary cases, logic gaps, or execution weaknesses surfaced before moving forward. |
| PM Consultant | [`PM-Consultant-Skill`](https://github.com/Willis1214/Skills/tree/PM-Consultant-Skill) | `1.1.0` | `v1.1.0`, 2026-05-18: reworked into a PRD-first, QC-gated requirement workflow. `v1.0.0` was the initial staged consulting release. | Clarifies requirements, user story maps, input/output contracts, boundaries, and QC checklists before implementation without prescribing the implementation path. | You need a confirmed PRD Markdown, user-story-map HTML, and QC checklist Markdown package before starting implementation. |
| Diff Output | [`Diff-Output-Skill`](https://github.com/Willis1214/Skills/tree/Diff-Output-Skill) | `1.0.0` | Initial public release, 2026-05-18. | A fixed comparison table for changes, before/after states, version differences, and update summaries. | You want a concise table showing `Type`, `Content`, `As is`, `To be`, and `Why`. |
| Program Asset Builder | [`Program-Asset-Builder-Skill`](https://github.com/Willis1214/Skills/tree/Program-Asset-Builder-Skill) | `1.1.0` | `v1.1.0`, 2026-05-13: switched final review, usage, and revision-history outputs to Chinese-first HTML. `v1.0.0` was the initial public release. | Packages known source code into an OpenCode-compatible program asset with review report, usage guide, revision history, intelligence, card, validation, and release gate. | You have a final or known-good program and need a structured handoff/reuse package. |
| Wechat Message | [`Wechat-Message-Skill`](https://github.com/Willis1214/Skills/tree/Wechat-Message-Skill) | `1.0.0` | Initial public release. | Sends a WeChat message through the visible macOS desktop WeChat app using a controlled keyboard workflow. | You need Codex to send a message to a named WeChat contact or group without private WeChat APIs or bridge services. |
| Token Gate | [`Token-Gate-Skill`](https://github.com/Willis1214/Skills/tree/Token-Gate-Skill) | `0.1.0` | Initial public release candidate, 2026-05-05. | Prevents avoidable high-token work before large scans, long logs, large documents, generated artifacts, OCR, or subagent-heavy tasks. | A task may consume a lot of context and a cheaper path can preserve the same final result. |
| Memory Governor | [`Memory-Governor-Skill`](https://github.com/Willis1214/Skills/tree/Memory-Governor-Skill) | `0.1.0` | Initial public release, 2026-05-18. | Governs long-term command memory by detecting reusable user rules, asking for approval, and writing approved entries to memory. | A user wants durable preferences, prohibitions, shortcuts, or workflow rules remembered across future Codex tasks. |
| Programing Intelligence | [`Programing-Intelligence-Skill`](https://github.com/Willis1214/Skills/tree/Programing-Intelligence-Skill) | `0.1.0` | Initial public release. | Extracts durable Program Unit Intelligence from a final accepted implementation. | A program is accepted or final, and you want reusable engineering knowledge captured for the finished solution, not temporary helper scripts. |

## Repository Layout

- `main`: catalog and usage overview.
- One branch per skill package.
- Branch names match the original public skill package names.

## Maintenance

When a skill changes, update its branch first, then update this catalog so readers can see the current version, revision history, purpose, and trigger conditions from `main`.
