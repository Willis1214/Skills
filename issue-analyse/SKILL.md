---
name: issue-analyse
description: Proof-first complaint challenge, issue-existence review, breakthrough strategy selection, case reconstruction, contract-boundary analysis, attribution, and communication framing. Use when the user asks to discuss an issue, challenge whether a reported issue really exists, restore what happened, identify missing proof, break out of a disputed or stuck investigation, analyze responsibility boundaries, determine whether the cause belongs to another owner, upstream dependency, environment, process, contract gap, or evidence gap, prepare objective wording, or reason through "is this my fault / not my issue / external cause / contract not violated" scenarios. Do not use for pure source-code release review, executable QC/UAT, generic risk review, legal advice, HR discipline, or requests to fabricate blame.
---

# Issue Analyse

## Purpose

Guide issue discussions toward objective, proof-backed issue challenge, breakthrough strategy selection, reconstruction, and attribution.

The skill first challenges whether the complaint or feedback actually proves a problem, then restores the factual scene, then selects a suitable breakthrough strategy for disputed or stuck cases, then tests whether the event should be treated as an issue, then checks contract and proof boundaries, and only then assigns attribution and communication wording. It must not fabricate proof, personalize blame, or force a conclusion that the available facts do not support.

Default operating discipline: do not accept `改代码`, `查 Bug`, or `我方先背锅` as the first move just because someone raised an issue. First run complaint challenge, scene reconstruction, breakthrough strategy selection, and evidence gating. Only after that decide whether the next action is local fix, upstream proof request, cross-owner review, process repair, or safe communication.

Default output should use Chinese labels. Use Chinese wording for user-facing fields such as `证据`, `待补证据`, `结论把握度`, `合同边界`, and `归因类型`. Keep English only for technical or workplace terms that are clearer as terms, such as `Owner`, `RACI`, `baseline`, `waiver`, `special handle`, `scope drift`, `release gate`, `ticket`, `commit`, and `checklist`.

## Core Workflow

### 1. 问题提出质疑门

Start by challenging the complaint, feedback, or alleged issue itself. Do not assume that a complaint means an issue exists.

Attack the alleged issue from these angles first:

- 提出源头: who raised the problem, what exactly they saw, and what they compared against;
- 问题真实性: whether the observation is reproducible, current, complete, and supported by primary proof;
- 过去是否存在: whether old releases, old upstream files, old templates, or legacy projects already had the same behavior;
- 现在是否存在: whether the current released product, current upstream, and current runtime still show the same behavior;
- 相关项目是否存在: whether sibling projects, copied baselines, reference projects, or peer versions show the same behavior;
- 评价基准: whether the complaint is based on contract/spec/SOP, old baseline, current upstream, customer expectation, or changed scope;
- 实质影响: whether the difference materially affects the agreed deliverable or is only a preference, enhancement, late change, duplicate, stale report, or unproven assumption.

If the alleged issue is not proven, classify it as `问题尚未成立`, not as another party's fault. If the challenge cannot be completed because proof is missing, output a concise `问题提出质疑` response with:

- `被提出的问题`;
- `质疑点`;
- `已知证据`;
- `待补证据`;
- `暂定判断`;
- `下一步最小追问`.

When the case involves customer complaints, legacy behavior, copied baselines, historical acceptance, special handling, or related-project comparison, read `references/investigation-methods.md` before giving a firm answer.

### 2. 现场还原门

After challenging the complaint, restore the scene before judging responsibility.

Capture what is known and what is still missing:

- 事件陈述: what happened according to the user;
- 当前投诉或观察: who complained, what they saw, and what they compared against;
- 已知事实: confirmed facts versus user memory;
- 关键未知: missing facts that could change the conclusion;
- 时间线: request, handoff, change, release, complaint, mitigation;
- 相关对象: product, version, file, upstream/downstream artifact, system, Owner;
- 可用证据: ticket, mail, chat, log, commit, release package, checklist, screenshot;
- 当前 contract 或 expected behavior: PRD, SOP, API contract, SLA, ticket acceptance, handoff agreement, waiver, known limitation.

If the scene is not sufficiently reconstructed, do not directly decide issue existence or attribution. Output a concise `现场还原` response with:

- `已知事实`;
- `关键缺口`;
- `待补证据`;
- `暂定假设`;
- `下一步最小追问`.

Ask only for the smallest missing facts needed for the next decision gate. Do not demand exhaustive evidence when a narrower question can move the analysis forward.

### 3. 假设地图

Before selecting a conclusion, list plausible explanations that fit the current facts.

Common hypothesis types include:

- true defect;
- complaint based on undefined or changed expectation;
- legacy latent issue;
- accepted deviation / waiver / special handle;
- upstream baseline drift;
- downstream release consistency gap;
- requester / scope drift;
- process / contract gap;
- evidence gap.

Mark each hypothesis as `待验证`, `较可能`, `已排除`, or `证据不足`. Do not collapse the case into one blame target before competing hypotheses are tested.

### 4. 破局策略选择门

Before accepting a local fix or blame target, decide whether the situation needs one of these breakthrough strategies. Use only strategies supported by the facts, system context, and proof strength.

| 方法 | 使用场景 | 最小动作 | 风险边界 |
| --- | --- | --- | --- |
| `冲突扩大法` | A single alleged issue traps the user in local self-defense. | Temporarily assume the other party's logic is true, then deduce what other modules, releases, sibling projects, or upstream/downstream steps should also fail. Ask why those expected systemic effects are absent or unreported. | Requires real system architecture context. Do not invent affected areas or use loose analogies as proof. |
| `底层溯源法` | The investigation is stuck on a surface error, inherited judgment, or "it happened, so it must be wrong" logic. | Keep asking why until reaching the actual judgment baseline: spec, contract, interface rule, physical/industry constraint, acceptance criterion, or system invariant. Challenge whether the other party's basis is valid in this scenario. | Stop when the next "why" becomes unsupported speculation or philosophical arguing. |
| `归因防御策略` | A mature, stable system is blamed after a sudden alarm or new failure. | Treat new external variables, upstream changes, abnormal inputs, environment shifts, and release/control changes as first-class hypotheses. Also state what self-side invariants, monitors, or regression proof are needed to defend the mature-system assumption. | This is not a license to shift blame. It only applies when the user's system is well understood and has stability evidence. |
| `困境转化法` | The case is a corner / edge / special case that exceeds one module or one person's handling boundary. | Reframe it as a system-evolution, design-boundary, or process-gap issue; propose a cross-owner review with fix owner, root-cause owner, and prevention owner separated. | Requires upward or lateral coordination. Do not escalate before showing why the issue exceeds a local action boundary. |

Recommended mapping:

- If the issue is newly raised and unproven, start with `冲突扩大法` plus complaint challenge.
- If the case is stuck after evidence collection, use `底层溯源法` to test the judgment baseline.
- If a long-running mature system is suddenly blamed, use `归因防御策略` with monitoring and regression proof.
- If the conclusion points to a corner case or systemic gap, use `困境转化法` instead of solo debugging.

### 5. 问题成立性审查

After the complaint challenge and scene reconstruction are sufficient, test whether the alleged issue exists.

Analyze from angles that can overturn issue existence:

- no deviation from expected behavior;
- expected behavior was never defined;
- behavior falls inside accepted tolerance, SLA, SOP, or known limitation;
- impact is not material enough to qualify as an issue;
- the event is duplicate, stale, already resolved, or not reproducible;
- the complaint is based on assumption rather than proof;
- the request is a change request, preference, or enhancement, not a defect;
- the user or requester changed scope after the fact.

If existence is not proven, classify as `问题尚未成立`, not as someone else's fault.

### 6. 合同 / 约定边界

Then analyze whether a contract exists and whether it was violated.

Contract can include:

- PRD, spec, SOP, checklist, ticket acceptance criteria;
- API/interface schema, input/output contract, version contract;
- handoff agreement, Owner responsibility, RACI matrix;
- deadline, SLA, scope boundary, dependency agreement;
- written chat/email decision accepted by stakeholders.

For each relevant party, separate:

- `约定已定义`: what was explicitly promised;
- `约定已遵守`: whether the party followed it;
- `约定缺口`: what was undefined or ambiguous;
- `约定漂移`: whether the expectation changed after execution;
- `交接缺口`: whether required upstream input or downstream acceptance was missing.

Do not treat a vague expectation as a violated contract. If the contract is unclear, classify the cause as `约定缺口` or `证据缺口`.

### 7. 证据链

Build a full proof chain before attribution.

Use latest available proof when timing matters. If current facts may have changed, verify from the latest local artifact, system record, ticket, log, message, source file, or live source before making a firm claim.

Classify proof strength:

- `直接证据`: logs, commits, tickets, timestamps, tests, screenshots, official records, written requirements;
- `相互印证`: multiple independent signals pointing the same way;
- `背景证据`: background that explains plausibility but does not prove cause;
- `弱证据`: memory, hearsay, single ambiguous observation, inferred intent;
- `缺失`: needed but unavailable.

Every attribution must cite proof. If proof is weak, say so and lower `结论把握度`.

### 8. 归因矩阵

Classify contributing factors without collapsing everything into one blame target:

| 归因类型 | Meaning |
| --- | --- |
| `我方责任` | The user's side violated a defined contract, missed a required step, or introduced the defect. |
| `其他 Owner 责任` | Another person/team/system Owner violated a defined contract or failed a required handoff. |
| `上游依赖` | Required upstream data, API, environment, permission, timing, or decision was missing or wrong. |
| `流程 / 约定缺口` | The issue came from undefined scope, ambiguous acceptance, missing Owner, or missing review gate. |
| `环境 / 外部因素` | Tooling, network, third-party service, policy, market, or runtime condition caused or materially contributed. |
| `需求方 / 范围漂移` | The requester changed expectations after execution or judged against a requirement not agreed earlier. |
| `证据缺口` | The cause cannot be safely assigned from available proof. |

Use RACI when useful:

- `Responsible`: who executed the task;
- `Accountable`: who owned final acceptance or decision;
- `Consulted`: who had required input;
- `Informed`: who needed notification only.

Distinguish ownership of the event from ownership of the fix. A party may own remediation without being the root cause.

### 9. 根因推理

Use 5 Whys only while proof supports each step.

Allow multiple contributing causes. Stop the chain when the next step becomes speculation. Mark unverified links as `待补证据`.

Do not overfit to the user's preferred conclusion. If the strongest proof points back to the user's side, state that directly and suggest a safer communication route.

### 10. 沟通边界

Produce wording that is objective and usable.

Always separate:

- `可说`: supported by proof and contract;
- `不应说`: unsupported, personal, speculative, or accusatory;
- `待补证据`: exact missing proof;
- `稳妥表达`: neutral wording that preserves credibility.

Prefer statements about facts, contract, handoff, proof, and next action. Avoid statements about motive, competence, laziness, or character.

## Output Contract

Read `references/output-template.md` for the required report format.

When the issue is sensitive, political, customer-facing, or likely to be forwarded, also read `references/communication-boundary.md`.

When attribution is complex or disputed, read `references/attribution-rubric.md` before assigning `结论把握度`.

When the issue requires deeper issue-reconstruction or breakthrough methods, such as legacy issues, historical acceptance, baseline drift, dependency expectations, complaint validity challenges, conflict expansion, root-baseline tracing, mature-system attribution defense, or corner-case transformation, read `references/investigation-methods.md`.

## Hard Boundaries

- Do not fabricate proof, quotes, logs, tickets, dates, contracts, owners, or intent.
- Do not help falsely assign known self-side responsibility to others.
- Do not output personal attacks or defamatory claims.
- Do not convert weak proof into firm blame.
- Do not use `归因防御策略` as unsupported blame shifting; it must be paired with self-side stability evidence and external-variable proof requests.
- Do not use `冲突扩大法` to manufacture hypothetical failures; only derive impacts that logically follow from the other party's stated premise.
- Do not give legal or HR disciplinary advice; provide evidence-organization and communication-risk framing only.
- Do not claim an issue is closed unless the complaint challenge, scene reconstruction, issue existence, contract boundary, proof chain, attribution, and conclusion certainty are all explicit.
