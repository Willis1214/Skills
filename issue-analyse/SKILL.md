---
name: issue-analyse
description: Evidence-first issue reconstruction, issue-existence review, contract-boundary analysis, attribution, and communication framing. Use when the user asks to discuss an issue, restore what happened, decide whether something is actually an issue, identify missing evidence, analyze responsibility boundaries, determine whether the cause belongs to another owner, upstream dependency, environment, process, contract gap, or evidence gap, prepare objective wording, or reason through "is this my fault / not my issue / external cause / contract not violated" scenarios. Do not use for pure source-code release review, executable QC/UAT, generic risk review, legal advice, HR discipline, or requests to fabricate blame.
---

# Issue Analyse

## Purpose

Guide issue discussions toward objective, evidence-backed reconstruction and attribution.

The skill first restores the factual scene, then tests whether the event should be treated as an issue, then checks contract and evidence boundaries, and only then assigns attribution and communication wording. It must not fabricate proof, personalize blame, or force a conclusion that the evidence does not support.

Default output should use Chinese labels. Keep English only for technical or workplace terms that are clearer as terms, such as `Evidence`, `Owner`, `RACI`, `Confidence`, `baseline`, `waiver`, `special handle`, `scope drift`, and `release gate`.

## Core Workflow

### 1. Case Reconstruction Gate

Start by restoring the scene before judging.

Capture what is known and what is still missing:

- 事件陈述: what happened according to the user;
- 当前投诉或观察: who complained, what they saw, and what they compared against;
- 已知事实: confirmed facts versus user memory;
- 关键未知: missing facts that could change the conclusion;
- 时间线: request, handoff, change, release, complaint, mitigation;
- 相关对象: product, version, file, upstream/downstream artifact, system, Owner;
- 可用 Evidence: ticket, mail, chat, log, commit, release package, checklist, screenshot;
- 当前 contract 或 expected behavior: PRD, SOP, API contract, SLA, ticket acceptance, handoff agreement, waiver, known limitation.

If the scene is not sufficiently reconstructed, do not directly decide issue existence or attribution. Output a concise `现场还原` response with:

- `已知事实`;
- `关键缺口`;
- `需补 Evidence`;
- `暂定假设`;
- `下一步最小追问`.

Ask only for the smallest missing facts needed for the next decision gate. Do not demand exhaustive evidence when a narrower question can move the analysis forward.

### 2. Hypothesis Map

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

When the issue involves legacy behavior, baseline changes, historical acceptance, customer complaints, special handling, owner handoff, or complex responsibility, read `references/investigation-methods.md` before giving a firm answer.

### 3. Issue Existence Review

After the scene is reconstructed enough, test whether the alleged issue exists.

Analyze from angles that can overturn issue existence:

- no deviation from expected behavior;
- expected behavior was never defined;
- behavior falls inside accepted tolerance, SLA, SOP, or known limitation;
- impact is not material enough to qualify as an issue;
- the event is duplicate, stale, already resolved, or not reproducible;
- the complaint is based on assumption rather than Evidence;
- the request is a change request, preference, or enhancement, not a defect;
- the user or requester changed scope after the fact.

If existence is not proven, classify as `问题尚未成立` / `Issue Not Established`, not as someone else's fault.

### 4. Contract Boundary

Then analyze whether a contract exists and whether it was violated.

Contract can include:

- PRD, spec, SOP, checklist, ticket acceptance criteria;
- API/interface schema, input/output contract, version contract;
- handoff agreement, Owner responsibility, RACI matrix;
- deadline, SLA, scope boundary, dependency agreement;
- written chat/email decision accepted by stakeholders.

For each relevant party, separate:

- `Contract Defined`: what was explicitly promised;
- `Contract Compliance`: whether the party followed it;
- `Contract Gap`: what was undefined or ambiguous;
- `Contract Drift`: whether the expectation changed after execution;
- `Handoff Gap`: whether required upstream input or downstream acceptance was missing.

Do not treat a vague expectation as a violated contract. If the contract is unclear, classify the cause as `Contract Gap` or `Evidence Gap`.

### 5. Evidence Chain

Build a full Evidence chain before attribution.

Use latest available Evidence when timing matters. If current facts may have changed, verify from the latest local artifact, system record, ticket, log, message, source file, or live source before making a firm claim.

Classify Evidence strength:

- `Direct`: logs, commits, tickets, timestamps, tests, screenshots, official records, written requirements;
- `Corroborating`: multiple independent signals pointing the same way;
- `Contextual`: background that explains plausibility but does not prove cause;
- `Weak`: memory, hearsay, single ambiguous observation, inferred intent;
- `Missing`: needed but unavailable.

Every attribution must cite Evidence. If Evidence is weak, say so and lower Confidence.

### 6. Attribution Matrix

Classify contributing factors without collapsing everything into one blame target:

| Attribution Type | Meaning |
| --- | --- |
| `Self` | The user's side violated a defined contract, missed a required step, or introduced the defect. |
| `Other Owner` | Another person/team/system Owner violated a defined contract or failed a required handoff. |
| `Upstream Dependency` | Required upstream data, API, environment, permission, timing, or decision was missing or wrong. |
| `Process / Contract Gap` | The issue came from undefined scope, ambiguous acceptance, missing Owner, or missing review gate. |
| `Environment / External` | Tooling, network, third-party service, policy, market, or runtime condition caused or materially contributed. |
| `Requester / Scope Drift` | The requester changed expectations after execution or judged against a requirement not agreed earlier. |
| `Evidence Gap` | The cause cannot be safely assigned from available Evidence. |

Use RACI when useful:

- `Responsible`: who executed the task;
- `Accountable`: who owned final acceptance or decision;
- `Consulted`: who had required input;
- `Informed`: who needed notification only.

Distinguish ownership of the event from ownership of the fix. A party may own remediation without being the root cause.

### 7. Root-Cause Reasoning

Use 5 Whys only while Evidence supports each step.

Allow multiple contributing causes. Stop the chain when the next step becomes speculation. Mark unverified links as `需补 Evidence`.

Do not overfit to the user's preferred conclusion. If the strongest Evidence points back to the user's side, state that directly and suggest a safer communication route.

### 8. Communication Boundary

Produce wording that is objective and usable.

Always separate:

- `可说`: supported by Evidence and contract;
- `不应说`: unsupported, personal, speculative, or accusatory;
- `还需补 Evidence`: exact missing proof;
- `稳妥表达`: neutral wording that preserves credibility.

Prefer statements about facts, contract, handoff, Evidence, and next action. Avoid statements about motive, competence, laziness, or character.

## Output Contract

Read `references/output-template.md` for the required report format.

When the issue is sensitive, political, customer-facing, or likely to be forwarded, also read `references/communication-boundary.md`.

When attribution is complex or disputed, read `references/attribution-rubric.md` before assigning Confidence.

When the issue requires deeper issue-reconstruction methods, such as legacy issues, historical acceptance, baseline drift, dependency expectations, or complaint validity challenges, read `references/investigation-methods.md`.

## Hard Boundaries

- Do not fabricate Evidence, quotes, logs, tickets, dates, contracts, owners, or intent.
- Do not help falsely assign known self-side responsibility to others.
- Do not output personal attacks or defamatory claims.
- Do not convert weak Evidence into firm blame.
- Do not give legal or HR disciplinary advice; provide evidence-organization and communication-risk framing only.
- Do not claim an issue is closed unless the scene, issue existence, contract boundary, Evidence chain, attribution, and Confidence are all explicit.
