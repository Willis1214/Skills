# Stage 1: Technical Consultation And Decision

## Goal

Clarify the project context, product boundary, users, inputs, outputs, runtime environment, version target, feasible technical paths, and decision records before any formal PRD or implementation.

## Required Response Structure

```markdown
## 核心决策记录

| 序号 | 决策项 | 当前结论 | 状态 |
| -- | -- | -- | -- |
| 1 | 项目类型 | TBD | 待确认 |
| 2 | 软件形态 | TBD | 待确认 |
| 3 | 技术栈 | TBD | 待确认 |
| 4 | 核心用户 | TBD | 待确认 |
| 5 | 关键边界 | TBD | 待确认 |

## 当前方案分析

| 方案 | 核心思路 | 优点 | 风险 / 边界 | 适用条件 |
| -- | -- | -- | -- | -- |
| 方案 A |  |  |  |  |
| 方案 B |  |  |  |  |
| 方案 C |  |  |  |  |

## 下一步引导

1. 
2. 
3. 
```

## First Reply Requirements

When the user provides the first business input for a project, prioritize these decision items:

| 序号 | 决策项 | 当前结论 | 状态 |
| -- | -- | -- | -- |
| 1 | 项目类型 | TBD | 待确认 |
| 2 | 软件形态 | TBD | 待确认 |
| 3 | 目标运行环境 | TBD | 待确认 |
| 4 | 第一版核心目标 | TBD | 待确认 |
| 5 | 输入输出边界 | TBD | 待确认 |

## Rules

- Record only confirmed or genuinely decision-relevant TBD items.
- If the user changes a decision, update the table and mark it as `已变更`.
- Analyze only one submodule or decision focus at a time.
- Provide 2-3 feasible paths when comparison helps.
- For engineering paths, cover maintainability, complexity, extensibility, verification method, and delivery risk.
- Ask 1-3 concrete confirmation questions.
- Do not output a full PRD, full code, UAT/QC, or retrospective in this stage.

