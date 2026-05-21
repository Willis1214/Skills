# 输出模板

默认使用中文字段。`Evidence`、`Owner`、`RACI`、`Confidence`、`baseline`、`waiver`、`special handle` 等词可以作为 technical terms 保留，但模板字段不要默认使用英文。

## 首次信息不足时

```markdown
## Issue Analyse｜现场还原

### 1. 已知事实
| 事实 | 来源 | 稳定性 |
| --- | --- | --- |
| <已确认或用户已描述的事实> | <Evidence / 口述 / 待核实> | 直接 / 间接 / 待验证 |

### 2. 关键缺口
| 缺口 | 为什么重要 | 不补会影响什么判断 |
| --- | --- | --- |
| <缺少的事实或材料> | <影响 issue / contract / attribution 哪一层> | <会导致 Confidence 降级或无法归因> |

### 3. 需补 Evidence
| Evidence | 优先级 | 用途 |
| --- | --- | --- |
| <ticket / mail / chat / log / commit / release package / checklist / screenshot> | 高 / 中 / 低 | <用于还原现场、确认 expected behavior、确认 actual behavior、确认影响、确认 Owner> |

### 4. 暂定假设
| 假设 | 当前依据 | 状态 |
| --- | --- | --- |
| <可能解释> | <已有 Evidence 或背景> | 待验证 / 较可能 / 已排除 / 证据不足 |

### 5. 下一步最小追问
- <只问能推动下一判断节点的最小问题>
```

## 信息足够时

```markdown
## Issue Analyse｜问题归因分析

### 1. 问题是否成立
| 字段 | 判断 |
| --- | --- |
| 被提出的问题 | <用户描述的问题> |
| 应然状态 | <expected behavior；未知写“未知”> |
| 实际状态 | <actual behavior；未知写“未知”> |
| 实质影响 | <影响；不足写“未证明达到 issue 级别”> |
| 初步结论 | 问题成立 / 问题尚未成立 / 需要补 Evidence |
| 理由 | <为什么成立、不成立或证据不足> |

### 2. 合同与边界
| 合同 / 约定项 | Owner | Evidence | 是否符合 | 缺口 |
| --- | --- | --- | --- | --- |
| <PRD / SOP / API contract / SLA / ticket / handoff agreement / 口头或书面约定> | <Owner> | <Evidence> | 已符合 / 已违反 / 未定义 / 需要补 Evidence | <缺口> |

### 3. Evidence 链
| Evidence | 来源 | 时间 | 支持的判断 | 强度 | 缺口 |
| --- | --- | --- | --- | --- | --- |
| <证据> | <来源> | <时间> | <支持哪个判断> | Direct / Corroborating / Contextual / Weak / Missing | <缺口> |

### 4. 归因矩阵
| 原因 | 归因类型 | Owner / RACI | Evidence | Confidence | 说明 |
| --- | --- | --- | --- | --- | --- |
| <原因> | Self / Other Owner / Upstream Dependency / Process / Contract Gap / Environment / External / Requester / Scope Drift / Evidence Gap | Responsible / Accountable / Consulted / Informed | <Evidence> | High / Medium / Low / Unknown | <说明> |

### 5. 沟通边界
| 类型 | 表达 |
| --- | --- |
| 可说 | <证据和合同支持的客观表述> |
| 不应说 | <不该说的推断、攻击或无证据归因> |
| 还需补 Evidence | <还需要补什么证据> |
| 稳妥表达 | <更稳妥、可转发的表达> |

### 6. 下一步行动
| 行动 | Owner | 目的 |
| --- | --- | --- |
| <行动> | <Owner> | <补证据/修合同/修流程/修问题> |
```

## 简短聊天版

如果用户只需要快速讨论，压缩为：

1. `现场还原`;
2. `问题是否成立`;
3. `合同与边界`;
4. `最强 Evidence`;
5. `可能归因`;
6. `可说 / 不应说 / 还需补 Evidence / 稳妥表达`.

当 `Confidence` 低于 `High` 时，不得省略 `还需补 Evidence`。
