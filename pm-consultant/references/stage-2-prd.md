# Stage 2: PRD Output

## Trigger

Use only when the user explicitly asks for a PRD, requirements document, development document, or formal document.

## Goal

Turn confirmed Stage 1 decisions into a developer-facing PRD. Mark unconfirmed content as `TBD`.

## Required Structure

```markdown
# PRD：{项目名称}

## 1. 文档概览

| 项目 | 内容 |
| -- | -- |
| 项目名称 |  |
| 文档版本 |  |
| 软件版本 |  |
| 文档状态 | Draft / Review / Final |
| 目标用户 |  |
| 运行环境 |  |

## 2. 项目背景

说明当前问题、业务痛点、已有流程缺陷，以及为什么需要该系统或功能。

## 3. 核心目标

| 目标 | 说明 | 验收标准 |
| -- | -- | -- |
| 目标 1 |  |  |
| 目标 2 |  |  |

## 4. 业务流程与逻辑

描述主要业务流、输入输出、处理步骤、异常路径。必要时使用 Mermaid 流程图。

## 5. 用户故事地图

| 用户角色 | 使用场景 | 用户目标 | 系统响应 |
| -- | -- | -- | -- |
|  |  |  |  |

## 6. 功能详细说明

| 功能模块 | 功能说明 | 输入 | 输出 | 处理逻辑 | 异常处理 |
| -- | -- | -- | -- | -- | -- |
|  |  |  |  |  |  |

## 7. 技术架构与数据结构

包括技术栈、模块划分、数据模型、文件结构、API / CLI 设计、配置项、日志与审计机制。

## 8. 非功能性需求

| 类型 | 要求 |
| -- | -- |
| 性能 |  |
| 安全 |  |
| 兼容性 |  |
| 可维护性 |  |
| 可测试性 |  |
| 可扩展性 |  |

## 9. 待确认问题

| 编号 | 问题 | 影响范围 | 优先级 |
| -- | -- | -- | -- |
| TBD-001 |  |  |  |
```

## Rules

- Do not invent missing requirements.
- Preserve user-provided terms, fields, constraints, and version labels.
- Keep `TBD` visible for unresolved decisions.
- If the PRD would be materially incomplete, state the blocking missing decisions before or inside section 9.

