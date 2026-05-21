# 沟通边界

Use this reference when the user asks how to explain an issue to another person, manager, customer, vendor, or upstream/downstream Owner.

## Safe Communication Principles

- Start by separating the raised complaint from the proven issue.
- Say what happened, when, and based on which proof.
- Tie responsibility to contract, Owner boundary, RACI role, handoff, or acceptance criteria.
- Separate cause from remediation.
- Separate facts from interpretations.
- Admit proof gaps before drawing conclusions.
- Prefer "当前证据支持" over absolute statements when `结论把握度` is not high.
- Prefer "合同没有定义该条件" over "对方失败/违规" when the contract is ambiguous.

## 默认输出字段

沟通口径默认使用中文字段：

| 中文字段 | 含义 |
| --- | --- |
| 可说 | 由证据和合同支撑、可以对外或对内表达的事实链 |
| 不应说 | 推测、攻击、动机判断、无证据归因或容易被反驳的说法 |
| 待补证据 | 若要提高结论把握度或升级归因，还必须补的证明 |
| 稳妥表达 | 更适合转发、会议或管理层沟通的中性版本 |

不要默认输出英文沟通字段名，除非用户明确要求英文模板。

## Phrases To Prefer

- `当前证据支持的判断是...`
- `目前只能证明有人提出了这个问题，尚未证明它构成交付缺陷。`
- `需要先确认过去版本、当前版本和相关 project 是否都有同样现象。`
- `从已定义的接口/验收标准看...`
- `该点更像是合同/范围未定义，而不是执行偏差。`
- `这个现象需要先补齐证据，暂时不能归因。`
- `上游输入在 <time> 前未满足约定，因此下游结果受影响。`
- `我们这边遵守了 <contract item>，但 <missing dependency> 不在当前控制范围内。`
- `修复 Owner 和原因 Owner 需要分开看。`

## Phrases To Avoid

- `这肯定不是我的问题` when proof is incomplete.
- `都是他们的问题` without contract and proof.
- `他们不专业 / 不负责 / 没能力`.
- `我猜是...` in stakeholder-facing wording.
- `这个不算 issue` without defining expected behavior and impact.
- `已经证明` when the strongest proof is only contextual or weak.

## If The User Wants A Stronger Position

Give the strongest defensible wording, not the strongest possible accusation.

Structure:

1. 先说问题提出是否经得起质疑。
2. 再说合同或合同缺口。
3. 再说证据和因果链。
4. 标注结论把握度。
5. 说明补什么证据才能升级结论。

Example:

```text
基于当前 ticket 记录和接口约定，A 输入在约定时间前未完成交付，这是导致 B 输出延迟的直接原因之一。目前结论把握度为中等，因为还缺少 A 系统侧原始日志；如果补到该日志，归因把握度可以提高。
```

## If Proof Points Back To The User

Do not hide it. Reframe toward controllable remediation:

```text
当前证据显示我们这边确实漏了 <step>，不适合把原因归给上游。更稳妥的说法是：本次问题由我方执行缺口触发，同时暴露出 checklist 没有强制校验 <condition>，后续通过 <action> 防止重复。
```
