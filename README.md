# Brainstorm

## English

Brainstorm is a Codex skill for turning unclear engineering or product ideas into a confirmed requirement package before implementation starts.

It keeps the proven PRD-first workflow from the former PM Consultant skill: clarify requirements, build a user story map, confirm the requirement contract, discuss QC coverage, run a Red Team gate, then produce final PRD/story-map/QC artifacts. The implementation path is intentionally not prescribed unless the user gives hard technical constraints.

### What It Does

- Clarifies project background, objective, users, inputs, outputs, boundaries, non-goals, runtime environment, constraints, and success criteria.
- Builds a user story map with roles, activities, tasks, system responses, process flow, condition architecture, exceptions, and edge cases.
- Summarizes confirmed information and unresolved `TBD` items for explicit user confirmation.
- Discusses a QC checklist before final output so acceptance criteria become part of the requirement contract.
- Runs the installed local `red-team` skill before final artifacts; if that skill recommends the `red-team` Sub Agent, the main Agent owns the spawn call and final integration.
- Runs the installed local `front-taste` skill when visual, UI, HTML, dashboard, deck, or decision-material quality matters; if that skill recommends the `front-taste` Sub Agent, the main Agent owns the spawn call and final integration.
- Produces a final three-artifact package:
  - PRD Markdown
  - user story map HTML
  - QC checklist Markdown table

### When To Use It

Use this skill when:

- you have a new system, tool, workflow, platform, or feature idea
- requirements are still ambiguous
- users, inputs, outputs, boundaries, and non-goals need to be clarified
- you want a PRD-ready package before implementation
- you need a user story map with flow and condition architecture
- you need a QC checklist that constrains acceptance without over-constraining implementation
- you need local Red Team and Front Taste modules to feed reviewed findings back into the main workflow

### When Not To Use It

Do not use this skill for:

- simple factual answers
- narrow bug fixes with already confirmed requirements
- formal code review findings
- ordinary GitHub repository publishing workflows
- cases where the user has already provided a complete PRD and only wants implementation

### Workflow

| Step | Name | Output | Gate |
| --- | --- | --- | --- |
| 1 | Requirement clarification | Confirmed fields and open questions | User confirms enough context |
| 2 | User story map | Draft story map and flow/condition model | User confirms story map direction |
| 3 | Structured confirmation | Requirement contract summary with confirmed and `TBD` items | User explicitly confirms or edits |
| 4 | QC checklist discussion | Draft QC checklist and severity rules | User confirms checklist coverage |
| 5 | Red Team review and remediation | Local `red-team` skill review plus remediation decisions | No unresolved `High` findings; user confirms Red Team pass |
| 6 | Final output package | PRD Markdown, user story map HTML, QC checklist Markdown, plus Front Taste review when visual quality matters | Artifacts generated and validated |

### Installation

Install from the central Skills repository branch:

```bash
npx skills add https://github.com/Willis1214/Skills/tree/Brainstorm-Skill --skill brainstorm
```

Or copy `brainstorm/` from this branch into your Codex skills directory.

### Usage Prompt

```text
Use $brainstorm to clarify requirements, build a user story map, confirm structured requirements, discuss QC checklist coverage, run the local Red Team skill and remediate high-risk findings, run the local Front Taste skill when visual quality matters, then output PRD Markdown, user-story-map HTML, and QC checklist Markdown without prescribing the implementation path.
```

### Repository Contents

- `brainstorm/SKILL.md`: core skill instructions and workflow gate.
- `brainstorm/agents/openai.yaml`: Codex app display metadata.
- `brainstorm/references/workflow.md`: workflow sequence, Red Team module, Front Taste module, and gate rules.
- `brainstorm/references/requirement-clarification.md`: requirement contract fields and clarification prompts.
- `brainstorm/references/confirmation-summary-template.md`: structured confirmation gate template.
- `brainstorm/references/prd-template.md`: final PRD Markdown template, including Red Team and Front Taste summaries.
- `brainstorm/references/user-story-map-template.html`: self-contained HTML story map template.
- `brainstorm/references/qc-checklist-template.md`: final QC checklist Markdown template with Red Team and Front Taste items.
- `brainstorm/references/final-output-contract.md`: final artifact contract and validation checklist.
- `manifest.json`: release metadata for this skill branch.
- `REVISION_HISTORY.md`: version history.

### Release Notes

#### v2.0.0 - 2026-06-11

- Renamed the real skill name, trigger, display name, package folder, and usage prompt from PM Consultant / `pm-consultant` to Brainstorm / `brainstorm`.
- Preserved the existing six-step PRD-first implementation path.
- Made Red Team a local-skill-first module: Brainstorm calls the installed `red-team` skill first, and that skill may recommend the `red-team` Sub Agent.
- Added Front Taste as a local-skill-first Step 6 validation module for visual, UI, HTML, dashboard, deck, and decision-material outputs.
- Updated PRD, confirmation, QC, and final-output templates so Red Team and Front Taste evidence can be carried into final artifacts.

#### v1.2.0 - 2026-06-03

- Added a Red Team review and remediation gate before final specification output.
- Moved final artifact generation from Step 5 to Step 6.
- Added `QC-011` to require Red Team high-risk closure before final output.
- Added a PRD Red Team Gate Summary so final artifacts can carry review evidence.

#### v1.1.0 - 2026-05-18

- Reworked the skill from a fixed five-stage consulting/code/UAT/retrospective flow into a PRD-first, QC-gated requirement workflow.
- Removed default code-design and retrospective stages.
- Added final output contract for PRD Markdown, user-story-map HTML, and QC checklist Markdown.

#### v1.0.0 - 2026-05-18

- Initial public release as PM Consultant.

### Safety and Boundaries

- The skill does not request or use credentials.
- The skill does not run commands or access external services by itself.
- It marks unresolved content as `TBD`.
- It constrains requirements and acceptance criteria, not implementation style.
- It does not generate final PRD, story-map HTML, or QC checklist files until the Red Team gate passes.
- Red Team and Front Taste are local-skill-first modules; Brainstorm does not bypass those skills by directly inventing Sub Agent work.

### License

No open-source license has been selected in this release. Treat the contents as all rights reserved unless the repository owner adds a license.

---

## 中文

Brainstorm 是一个 Codex skill，用于把仍然模糊的工程或产品想法，在进入实现前整理成确认过的需求包。

它保留原 PM Consultant 已验证的 PRD-first 工作流：需求澄清、用户故事地图、结构化确认、QC Checklist 讨论、Red Team gate、最终三件套输出。它不规定具体实现路径，除非用户明确提供硬性技术约束。

### 它做什么

- 澄清项目背景、目标、用户、输入、输出、边界、非目标、运行环境、约束和成功标准。
- 建立用户故事地图，包括角色、活动、任务、系统响应、流程、条件架构、异常和边界场景。
- 汇总已确认信息和未解决的 `TBD` 项，要求用户二次确认。
- 在最终输出前讨论 QC Checklist，让验收标准成为需求合同的一部分。
- 最终文件前先调用本地 `red-team` skill；如果该 skill 建议调用 `red-team` Sub Agent，则由主 Agent 负责 spawn、整合和最终判断。
- 当视觉、UI、HTML、dashboard、deck 或决策材料质量相关时，调用本地 `front-taste` skill；如果该 skill 建议调用 `front-taste` Sub Agent，则由主 Agent 负责 spawn、整合和最终判断。
- 最终输出三件套：
  - PRD Markdown
  - 用户故事地图 HTML
  - QC Checklist Markdown table

### 什么时候使用

适用于：

- 新系统、新工具、新流程、新平台或新功能想法
- 需求仍然模糊
- 需要澄清用户、输入、输出、边界和非目标
- 需要在实现前形成 PRD-ready package
- 需要带流程和条件架构的用户故事地图
- 需要用 QC Checklist 限制验收，而不是限制实现路径
- 需要把本地 Red Team 和 Front Taste 模块的审查结果回灌到主流程

### 什么时候不使用

不适用于：

- 简单事实问答
- 需求已确认的窄范围 bug 修复
- 正式代码审查 findings
- 普通 GitHub 仓库发布流程
- 用户已经提供完整 PRD 且只需要实现的场景

### 工作流

| Step | 名称 | 输出 | Gate |
| --- | --- | --- | --- |
| 1 | 需求澄清 | 已确认字段和开放问题 | 用户确认上下文足够进入故事地图 |
| 2 | 用户故事地图 | Draft story map 和流程/条件模型 | 用户确认故事地图方向 |
| 3 | 结构化确认 | 含已确认项和 `TBD` 的需求合同摘要 | 用户明确确认或修改 |
| 4 | QC Checklist 讨论 | Draft QC checklist 和严重等级规则 | 用户确认 checklist 覆盖范围 |
| 5 | Red Team review and remediation | 本地 `red-team` skill 审查与修复决策 | 无未解决 `High` findings，且用户确认 Red Team pass |
| 6 | 最终三件套输出 | PRD Markdown、用户故事地图 HTML、QC Checklist Markdown；视觉质量相关时加入 Front Taste review | 文件生成并验证 |

### 安装

从中央 Skills 仓库分支安装：

```bash
npx skills add https://github.com/Willis1214/Skills/tree/Brainstorm-Skill --skill brainstorm
```

也可以把本分支的 `brainstorm/` 复制到本地 Codex skills 目录。

### 使用 Prompt

```text
Use $brainstorm to clarify requirements, build a user story map, confirm structured requirements, discuss QC checklist coverage, run the local Red Team skill and remediate high-risk findings, run the local Front Taste skill when visual quality matters, then output PRD Markdown, user-story-map HTML, and QC checklist Markdown without prescribing the implementation path.
```

### 仓库内容

- `brainstorm/SKILL.md`: 核心 skill 指令与 workflow gate。
- `brainstorm/agents/openai.yaml`: Codex app 展示 metadata。
- `brainstorm/references/workflow.md`: 工作流顺序、Red Team 模块、Front Taste 模块与 gate 规则。
- `brainstorm/references/requirement-clarification.md`: 需求合同字段与澄清问题。
- `brainstorm/references/confirmation-summary-template.md`: 结构化确认 gate 模板。
- `brainstorm/references/prd-template.md`: 最终 PRD Markdown 模板，包含 Red Team 和 Front Taste 摘要。
- `brainstorm/references/user-story-map-template.html`: 自包含 HTML 用户故事地图模板。
- `brainstorm/references/qc-checklist-template.md`: 包含 Red Team 和 Front Taste 检查项的 QC Checklist Markdown 模板。
- `brainstorm/references/final-output-contract.md`: 最终产物合同与验证清单。
- `manifest.json`: 当前 skill 分支的 release metadata。
- `REVISION_HISTORY.md`: 版本历史。

### Release Notes

#### v2.0.0 - 2026-06-11

- 将真实 skill 名、触发名、展示名、包目录和使用 prompt 从 PM Consultant / `pm-consultant` 改为 Brainstorm / `brainstorm`。
- 保留原有六步 PRD-first 实现路径。
- 将 Red Team 明确为 local-skill-first 模块：Brainstorm 先调用本地 `red-team` skill，再由该 skill 建议是否调用 `red-team` Sub Agent。
- 增加 Front Taste 作为 Step 6 的 local-skill-first 验证模块，适用于视觉、UI、HTML、dashboard、deck 和决策材料输出。
- 更新 PRD、结构化确认、QC 和最终输出模板，让 Red Team 与 Front Taste 证据可进入最终产物。

#### v1.2.0 - 2026-06-03

- 在最终规格文件输出前增加 Red Team review and remediation gate。
- 将最终文件生成从 Step 5 顺延到 Step 6。
- 增加 `QC-011`，要求 Red Team high-risk closure 后才能最终输出。
- 在 PRD 模板中增加 Red Team Gate Summary。

#### v1.1.0 - 2026-05-18

- 将 skill 从固定五阶段咨询/代码/UAT/复盘流程改为 PRD-first、QC-gated 的需求工作流。
- 移除默认代码设计和复盘阶段。
- 增加 PRD Markdown、用户故事地图 HTML、QC Checklist Markdown 的最终输出合同。

#### v1.0.0 - 2026-05-18

- 以 PM Consultant 名称首次公开发布。

### 安全与边界

- 该 skill 不请求或使用凭证。
- 该 skill 本身不运行命令或访问外部服务。
- 未解决内容标为 `TBD`。
- 它约束需求和验收标准，不约束实现风格。
- Red Team gate 未通过前，不生成最终 PRD、用户故事地图 HTML 或 QC Checklist 文件。
- Red Team 和 Front Taste 是 local-skill-first 模块；Brainstorm 不绕过这些 skill 直接编造 Sub Agent 任务。

### License

当前版本尚未选择开源 License。在仓库所有者添加 License 前，请按 all rights reserved 处理。
