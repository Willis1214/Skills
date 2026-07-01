# Brainstorm

Brainstorm is a Codex skill for clarifying complex engineering or product ideas before implementation starts. It turns loose goals into a confirmed requirement package, risk review, and final PRD/story-map/QC artifacts without prescribing the implementation path.

## What Changed In v2.1.0

Version `2.1.0` updates Brainstorm from a serial step-by-step discussion flow into a repeatable round loop. Every discussion round now covers requirement clarification, story/flow mapping, structured confirmation, QC thinking, and risk attack in one fixed role-based format. The final package phase still requires the local Red Team gate, optional Front Taste review when visual quality matters, and validated output artifacts.

## What It Helps With

- Clarifying project background, business objective, users, inputs, outputs, boundaries, non-goals, runtime context, and acceptance criteria.
- Mapping user stories, process flow, system responses, condition branches, exceptions, and edge cases.
- Keeping confirmed information and unresolved `TBD` items visible.
- Adding QC and acceptance thinking before implementation.
- Attacking assumptions and scope drift before final artifacts.
- Producing a final package only after the requirement direction is confirmed and gates have passed.

## When To Use It

Use this skill when:

- an idea is still ambiguous and needs structured clarification;
- a product, workflow, tool, platform, or feature needs a PRD-ready package;
- user roles, story flow, boundaries, and QC criteria are not yet clear;
- you need Red Team review before final artifacts;
- visual, UI, HTML, dashboard, deck, or decision-material quality needs Front Taste review before delivery.

## When Not To Use It

Do not use it for:

- simple factual answers;
- narrow bug fixes with already confirmed requirements;
- normal code review findings;
- GitHub publishing workflows;
- implementation-only tasks where the user already provided a complete PRD.

## Discussion Round Format

Every discussion round uses the fixed role-based format in `brainstorm/references/discussion-output-format.md`:

- `🧭 主持人`
- `📝 记录者`
- `💡 补充者（用户视角）`
- `💡 补充者（交付视角）`
- `💡 补充者（系统视角）`
- `🧱 边界官`
- `⚔️ 攻击者`
- `📌 汇总者`

The role labels are part of the runtime contract. They keep each round readable while preserving depth across requirements, story/flow, confirmation, QC, and risk review.

## Final Outputs

After the round loop produces a confirmed package and the required gates pass, Brainstorm writes:

- `output/<project_slug>_prd.md`
- `output/<project_slug>_user_story_map.html`
- `output/<project_slug>_qc_checklist.md`

The HTML story map is self-contained. Markdown artifacts stay directly editable.

## Installation

Install from this branch:

```bash
npx skills add https://github.com/Willis1214/Skills/tree/Brainstorm-Skill --skill brainstorm
```

Or copy the `brainstorm/` folder from this branch into your local Codex skills directory.

## Usage Prompt

```text
Use $brainstorm to run repeated discussion rounds in the fixed role-based format; every round covers requirement clarification, story and flow mapping, structured confirmation, QC and acceptance thinking, and risk attack without prescribing the implementation path. When the package is ready, run the local Red Team skill, run the local Front Taste skill when visual quality matters, then output PRD Markdown, user-story-map HTML, and QC checklist Markdown.
```

## Repository Contents

- `brainstorm/SKILL.md`: core instructions, boundaries, workflow, and output rules.
- `brainstorm/agents/openai.yaml`: Codex app metadata.
- `brainstorm/references/workflow.md`: round-loop and final package workflow.
- `brainstorm/references/discussion-output-format.md`: fixed role-based discussion format.
- `brainstorm/references/requirement-clarification.md`: requirement field guidance.
- `brainstorm/references/confirmation-summary-template.md`: structured confirmation template.
- `brainstorm/references/prd-template.md`: PRD template.
- `brainstorm/references/user-story-map-template.html`: self-contained story-map HTML template.
- `brainstorm/references/qc-checklist-template.md`: QC checklist template.
- `brainstorm/references/final-output-contract.md`: final artifact contract and validation checklist.
- `manifest.json`: branch release metadata.
- `REVISION_HISTORY.md`: version history.

## Safety And Boundaries

- Brainstorm does not request or use credentials.
- It marks unresolved content as `TBD`.
- It constrains requirements and acceptance criteria, not implementation style.
- It does not generate final artifacts until the round loop has enough confirmed context and the required review gates pass.
- Red Team and Front Taste are local-skill-first modules. Brainstorm does not bypass those skills by inventing direct subagent work.

## License

No open-source license has been selected in this release. Treat the contents as all rights reserved unless the repository owner adds a license.
