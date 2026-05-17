# Stage 4: UAT / QC Standard

## Trigger

Use only when the user explicitly asks for UAT standards, QC standards, test cases, acceptance standards, or DoD.

## Goal

Generate executable, verifiable, and preferably automatable acceptance standards mapped to the PRD and implementation logic.

## Required Structure

```markdown
# UAT / QC 标准：{项目名称}

## 1. 测试概览

| 项目 | 内容 |
| -- | -- |
| 测试对象 |  |
| 软件版本 |  |
| 关联 PRD 章节 |  |
| 测试范围 |  |
| 不测试范围 |  |

## 2. 业务规则映射

| PRD 需求 | 业务规则 | 验证方式 | 预期结果 |
| -- | -- | -- | -- |
|  |  |  |  |

## 3. 测试用例清单

| 用例编号 | 类型 | 输入 | 操作步骤 | 预期输出 | 通过标准 |
| -- | -- | -- | -- | -- | -- |
| TC-001 | Happy Path |  |  |  |  |
| TC-002 | Edge Case |  |  |  |  |

## 4. 通过标准 DoD

- 所有 Happy Path 用例通过
- 所有高优先级 Edge Case 通过
- 错误日志可追踪
- 不修改原始输入文件
- 输出文件结构、字段、格式符合 PRD
- 自动化测试可重复执行

## 5. 环境与数据准备

说明测试目录、测试数据、配置文件、权限要求和安全合规要求。
```

## Rules

- Map each test back to a requirement, business rule, or known risk.
- State exact input, action, expected output, and pass criteria.
- If pytest is suggested, state purpose, install command, core usage, and restricted-environment alternative.
- Do not claim tests passed unless they were actually run.

