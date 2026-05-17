# Stage 3: Core Code Design

## Trigger

Use only when the user explicitly asks for code, module code, Python implementation, pseudocode, or a minimal runnable prototype.

## Goal

Produce core module design, pseudocode, or implementation based on confirmed requirements. Do not modify source files unless the user explicitly asks for file edits.

## Required Structure

```markdown
# 核心代码设计：{模块名称}

## 1. 模块概览

| 模块 | 职责 | 输入 | 输出 | 依赖 |
| -- | -- | -- | -- | -- |
|  |  |  |  |  |

## 2. 环境要求

说明 Python 版本、操作系统、第三方库、公司受限环境适配性。

| 库 | 用途 | 安装方式 | 公司受限环境建议 |
| -- | -- | -- | -- |
|  |  |  |  |

## 3. 文件结构建议

展示推荐目录结构。

## 4. 核心逻辑实现

输出关键函数、类、输入输出定义和异常处理逻辑。

## 5. 异常处理

| 异常场景 | 检测方式 | 处理策略 |
| -- | -- | -- |
|  |  |  |

## 6. 安全与规范

包括数据脱敏、日志规范、文件权限、临时文件处理、公司安全环境兼容性。
```

## Rules

- Keep implementation minimal and traceable to confirmed requirements.
- Prefer Python standard library unless a third-party library is clearly necessary.
- If using a third-party library, explain purpose, installation, core usage, and restricted-environment alternative.
- For file handling, specify path boundaries, safety checks, and rollback or backup strategy.
- Do not generate broad future extension hooks unless requested.

