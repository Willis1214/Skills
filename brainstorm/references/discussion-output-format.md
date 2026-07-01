# Brainstorm Discussion Output Format

Use this format for every discussion-round chat response. Keep the role labels, role order, and field labels stable. Do not use Markdown tables or table headers in this process format.

## Fixed Round Template

```markdown
🧭 主持人
当前环节：
本轮问题：
推进规则：

📝 记录者
已确认：
   1. ……
   2. ……
已变更：
   1. ……
   2. ……
TBD：
   1. ……
   2. ……

💡 补充者（用户视角）
补充内容：
   1. ……
   2. ……

💡 补充者（交付视角）
补充内容：
   1. ……
   2. ……

💡 补充者（系统视角）
补充内容：
   1. ……
   2. ……

🧱 边界官
明确不做：
   1. ……
   2. ……

⚔️ 攻击者
风险：
   1. ……
   2. ……

📌 汇总者
本页产出：
   1. ……
   2. ……
下一步：
```

## Use Rules

- Keep every section even when content is sparse.
- Use `无` when a section has no material content for the current round.
- Use `TBD` exactly for unresolved requirement, boundary, evidence, or acceptance content.
- Every round must cover all five task classes at the strongest useful depth for the current context: requirement clarification, story / flow mapping, structured confirmation, QC / acceptance thinking, and risk attack.
- Ask only the next 1-3 questions needed to strengthen the current package, and place them under `📌 汇总者 / 下一步`.
- Record changed decisions under `📝 记录者 / 已变更` instead of silently replacing earlier conclusions.
- Split every user-provided perspective into a separate `💡 补充者（...视角）` role. Do not merge multiple perspectives under one `补充者` block.
- Use the same role-label style for every role: emoji + role name, without Markdown heading markers such as `##`.
- Put QC gates, acceptance details, evidence needs, and minimal validation detail under `💡 补充者（交付视角）`, not under `📌 汇总者`.
- Put non-goals, forbidden assumptions, untouched terms, and scope boundaries under `🧱 边界官`.
- Put adversarial concerns under `⚔️ 攻击者`; before final artifacts, still follow the Red Team gate and local `red-team` skill contract.
- Keep `📌 汇总者` compressed. It may list which outputs were produced on this page, such as confirmed items, changed decisions, split perspectives, TBD items, risk items, acceptance checks, or next questions, but it must not repeat the detailed content, evidence, reasoning, or risk explanations already covered by earlier roles.

## Final Packaging Prompt

When the repeated discussion rounds have produced a confirmed package that is ready for final output, actively ask whether to organize the discussion into final artifacts:

```markdown
## 📦 产出整理建议
当前讨论已经足够收拾成正式产物。建议生成：

1. PRD Markdown
2. User Story Map HTML
3. QC Checklist Markdown
4. 未决事项 TBD 清单

是否现在整理成文件？
```
