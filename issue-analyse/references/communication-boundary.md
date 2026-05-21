# 沟通边界

Use this reference when the user asks how to explain an issue to another person, manager, customer, vendor, or upstream/downstream Owner.

## Safe Communication Principles

- Say what happened, when, and based on which Evidence.
- Tie responsibility to contract, Owner boundary, RACI role, handoff, or acceptance criteria.
- Separate cause from remediation.
- Separate facts from interpretations.
- Admit Evidence gaps before drawing conclusions.
- Prefer "当前证据显示" over absolute statements when Confidence is not High.
- Prefer "合同没有定义该条件" over "对方失败/违规" when the contract is ambiguous.

## 默认输出字段

沟通口径默认使用中文字段：

| 中文字段 | 含义 |
| --- | --- |
| 可说 | 由 Evidence 和 contract 支撑、可以对外或对内表达的事实链 |
| 不应说 | 推测、攻击、动机判断、无证据归因或容易被反驳的说法 |
| 还需补 Evidence | 若要提高 Confidence 或升级归因，还必须补的证明 |
| 稳妥表达 | 更适合转发、会议或管理层沟通的中性版本 |

不要默认输出 `Can Say / Should Not Say / Need More Evidence / Safe Framing` 作为字段名，除非用户明确要求英文模板。

## Phrases To Prefer

- `当前证据支持的判断是...`
- `从已定义的接口/验收标准看...`
- `该点更像是合同/范围未定义，而不是执行偏差。`
- `这个现象需要先补齐 Evidence，暂时不能归因。`
- `上游输入在 <time> 前未满足约定，因此下游结果受影响。`
- `我们这边遵守了 <contract item>，但 <missing dependency> 不在当前控制范围内。`
- `修复 Owner 和原因 Owner 需要分开看。`

## Phrases To Avoid

- `这肯定不是我的问题` when Evidence is incomplete.
- `都是他们的问题` without contract and Evidence.
- `他们不专业 / 不负责 / 没能力`.
- `我猜是...` in stakeholder-facing wording.
- `这个不算 issue` without defining expected behavior and impact.
- `已经证明` when the strongest Evidence is only contextual or weak.

## If The User Wants A Stronger Position

Give the strongest defensible wording, not the strongest possible accusation.

Structure:

1. 先说合同或合同缺口。
2. 再说 Evidence。
3. 再说因果链。
4. 标注 Confidence。
5. 说明补什么 Evidence 才能升级结论。

Example:

```text
基于当前 ticket 记录和接口约定，A 输入在约定时间前未完成交付，这是导致 B 输出延迟的直接原因之一。当前 Confidence 为 Medium，因为还缺少 A 系统侧原始日志；如果补到该日志，归因可升级为 High。
```

## If Evidence Points Back To The User

Do not hide it. Reframe toward controllable remediation:

```text
当前证据显示我们这边确实漏了 <step>，不适合把原因归给上游。更稳妥的说法是：本次问题由我方执行缺口触发，同时暴露出 checklist 没有强制校验 <condition>，后续通过 <action> 防止重复。
```
