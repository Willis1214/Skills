# PM Consultant

## English

PM Consultant is a Codex skill for staged product-management and technical-architecture consultation.

It helps complex engineering ideas move from vague intent to:

1. technical consultation and decision records
2. PRD
3. core code design or pseudocode
4. UAT / QC standards
5. project retrospective

The skill is intentionally stage-gated. It does not jump to a full PRD, code, tests, or retrospective unless the user explicitly triggers that stage.

### What It Does

- Clarifies product type, software form, runtime environment, core users, inputs, outputs, version target, and key boundaries.
- Maintains compact decision records.
- Compares 2-3 feasible technical or product paths when needed.
- Produces structured PRD, code-design, UAT/QC, and retrospective outputs only after explicit stage triggers.
- Marks unknown or unconfirmed content as `TBD`.

### When To Use It

Use this skill when discussing:

- a new system, tool, workflow, platform, or feature
- product or technical architecture choices
- PRD preparation
- core module design or pseudocode
- UAT / QC criteria
- project retrospectives and methodology summaries

### When Not To Use It

Do not use this skill for:

- single-line factual answers
- narrow code bug fixes without product or architecture ambiguity
- formal code review findings
- direct implementation tasks where requirements are already fully specified
- normal repository publishing workflows

### Installation

Install from this repository:

```bash
npx skills add https://github.com/Willis1214/PM-Consultant-Skill --skill pm-consultant
```

Or copy `pm-consultant/` into your Codex skills directory.

### Usage Prompt

```text
Use $pm-consultant to guide this engineering idea through staged consultation, decision records, PRD, code design, UAT/QC, and retrospective without jumping stages.
```

### Repository Contents

- `pm-consultant/SKILL.md`: core skill instructions and stage router.
- `pm-consultant/agents/openai.yaml`: Codex app display metadata.
- `pm-consultant/references/stage-1-consulting.md`: Stage 1 consultation and decision template.
- `pm-consultant/references/stage-2-prd.md`: Stage 2 PRD template.
- `pm-consultant/references/stage-3-code-design.md`: Stage 3 core code design template.
- `pm-consultant/references/stage-4-uat-qc.md`: Stage 4 UAT/QC template.
- `pm-consultant/references/stage-5-retrospective.md`: Stage 5 retrospective template.
- `manifest.json`: release metadata for this public skill repository.

### Release Notes

#### v1.0.0 - 2026-05-18

- Initial public release.
- Adds the `pm-consultant` installable skill with display name `PM Consultant`.
- Defines five explicit stages: consultation, PRD, code design, UAT/QC, and retrospective.
- Adds stage-specific reference templates.
- Keeps the skill instruction-only with no scripts, assets, credentials, or external services.

### Safety and Boundaries

- The skill does not request or use credentials.
- The skill does not run commands or access external services by itself.
- It marks unknowns as `TBD` and avoids inventing unconfirmed facts.
- It does not override project-specific coding, testing, logging, or publishing rules.

### License

No open-source license has been selected in this release. Treat the contents as all rights reserved unless the repository owner adds a license.

---

## 中文

PM Consultant 是一个 Codex skill，用于复杂工程项目的阶段式产品管理与技术架构咨询。

它帮助把模糊想法逐步推进为：

1. 技术咨询与决策记录
2. PRD
3. 核心代码设计或伪代码
4. UAT / QC 标准
5. 项目复盘

该 skill 强制阶段门控。除非用户明确触发对应阶段，否则不会直接跳到完整 PRD、代码、测试标准或复盘报告。

### 它做什么

- 澄清项目类型、软件形态、运行环境、核心用户、输入输出、目标版本和关键边界。
- 维护紧凑的核心决策记录。
- 在需要时比较 2-3 个产品或技术方案。
- 只有在用户明确触发阶段后，才输出 PRD、代码设计、UAT/QC 或复盘。
- 对未确认内容标记 `TBD`。

### 什么时候使用

适用于：

- 新系统、新工具、新流程、新平台或新功能讨论
- 产品或技术架构选型
- PRD 准备
- 核心模块设计或伪代码
- UAT / QC 标准
- 项目复盘与方法论沉淀

### 什么时候不使用

不适用于：

- 单句事实问答
- 没有产品或架构歧义的窄范围代码修复
- 正式代码审查 findings
- 需求已经完全明确的直接实现任务
- 普通 GitHub 仓库发布流程

### 安装

从本仓库安装：

```bash
npx skills add https://github.com/Willis1214/PM-Consultant-Skill --skill pm-consultant
```

也可以把 `pm-consultant/` 复制到本地 Codex skills 目录。

### 使用 Prompt

```text
Use $pm-consultant to guide this engineering idea through staged consultation, decision records, PRD, code design, UAT/QC, and retrospective without jumping stages.
```

### 仓库内容

- `pm-consultant/SKILL.md`: 核心 skill 指令与阶段路由。
- `pm-consultant/agents/openai.yaml`: Codex app 展示 metadata。
- `pm-consultant/references/stage-1-consulting.md`: 阶段一咨询与决策模板。
- `pm-consultant/references/stage-2-prd.md`: 阶段二 PRD 模板。
- `pm-consultant/references/stage-3-code-design.md`: 阶段三核心代码设计模板。
- `pm-consultant/references/stage-4-uat-qc.md`: 阶段四 UAT/QC 模板。
- `pm-consultant/references/stage-5-retrospective.md`: 阶段五复盘模板。
- `manifest.json`: 公开 skill 仓库的 release metadata。

### Release Notes

#### v1.0.0 - 2026-05-18

- 首次公开发布。
- 新增 installable skill `pm-consultant`，展示名为 `PM Consultant`。
- 定义五个明确阶段：咨询、PRD、代码设计、UAT/QC、复盘。
- 新增阶段专用 reference templates。
- 保持 instruction-only，不需要脚本、资产、凭证或外部服务。

### 安全与边界

- 该 skill 不请求或使用凭证。
- 该 skill 本身不运行命令，也不访问外部服务。
- 对未知内容标记 `TBD`，避免编造未确认事实。
- 不覆盖项目自身的编码、测试、日志或发布规则。

### License

本版本未选择开源 License。除非仓库所有者后续添加 License，否则按 all rights reserved 处理。
