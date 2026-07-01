# Revision History

## v2.1.0 - 2026-07-01

| Field | Value |
| --- | --- |
| Version | v2.1.0 |
| Date | 2026-07-01 |
| Change Type | Runtime contract update |
| Repository | Willis1214/Skills |
| Branch | Brainstorm-Skill |

### Summary

Updated Brainstorm from a serial step workflow into a repeatable discussion round loop. Each round now covers requirement clarification, story/flow mapping, structured confirmation, QC thinking, and risk attack in a fixed role-based format.

### Source Skill Changes

- Updated `SKILL.md` description and workflow rules for the round-loop model.
- Replaced old step-by-step discussion output with the fixed role format.
- Added `references/discussion-output-format.md`.
- Updated `references/workflow.md` to describe round-loop operation and final package gating.
- Updated `agents/openai.yaml` default prompt to reflect the new round-loop trigger.
- Preserved final PRD/story-map/QC output contract and local-skill-first Red Team / Front Taste gates.

### Compatibility

- Installable skill name remains `brainstorm`.
- Branch remains `Brainstorm-Skill`.
- Existing final artifact paths remain unchanged.
- Users should expect discussion rounds to be role-based instead of old compact step tables.

### Validation

- Local `SKILL.md` frontmatter parsed.
- `agents/openai.yaml` parsed.
- `manifest.json` parsed.
- Staged file list checked.
- Remote branch and catalog verification are recorded in the publish report for this release.

### Known Gaps

- No open-source license has been selected.
- Legacy `PM-Consultant-Skill` branch cleanup remains out of scope.

## v2.0.0 - 2026-06-11

Renamed the real skill identity from PM Consultant / `pm-consultant` to Brainstorm / `brainstorm`, while preserving the existing PRD-first implementation path. Added local-skill-first Red Team and Front Taste routing.

## v1.2.0 - 2026-06-03

Added a Red Team review and remediation gate before final PRD, user story map, and QC checklist output.

## v1.1.0 - 2026-05-18

Reworked PM Consultant from a fixed consulting/code/UAT/retrospective flow into a PRD-first, QC-gated requirement workflow.

## v1.0.0 - 2026-05-18

Initial public release as PM Consultant.
