# Attribution Rubric

Use this rubric when assigning responsibility, objective causes, or Confidence.

## Decision Order

1. Existence: Does the alleged issue exist as a deviation from a defined expectation?
2. Contract: Which explicit contract, boundary, or acceptance criterion applies?
3. Compliance: Who did or did not follow the contract?
4. Causality: Which event or missing input materially caused the observed impact?
5. Evidence: Which facts prove or weaken that attribution?
6. Confidence: How strong is the conclusion?

Do not skip existence or contract review. Many disputes are not defects; they are undefined expectations, changed scope, or missing acceptance criteria.

## Issue Existence Tests

Classify as `Issue Not Established` when one or more apply:

- expected behavior is absent or ambiguous;
- actual behavior matches documented behavior;
- reported impact is outside agreed scope;
- severity is below the issue threshold;
- reproduction is absent and no direct Evidence exists;
- the request is better classified as enhancement, preference, or late scope change;
- the claim depends on outdated Evidence.

Classify as `Issue Established` only when there is a concrete expected-vs-actual gap with material impact.

## Contract Tests

Use `Contract Violation` only when all are true:

- a contract existed before the event;
- the responsible party had access to the contract;
- the contract covered the disputed condition;
- the party's action or omission violated it;
- the violation materially contributed to the impact.

Use `Contract Gap` when expectations were undefined, ambiguous, conflicting, or changed after execution.

Use `Contract Complied` when the party followed the defined contract even if the outcome disappointed someone.

## Evidence Strength

| Strength | Criteria | Confidence Ceiling |
| --- | --- | --- |
| `Direct` | Primary record proves the fact: ticket, log, commit, test result, timestamp, accepted spec, written decision | High |
| `Corroborating` | Multiple independent signals align, but no single primary record proves the whole chain | Medium-High |
| `Contextual` | Background supports plausibility only | Medium |
| `Weak` | Memory, hearsay, ambiguous observation, single non-primary signal | Low |
| `Missing` | Required proof is absent | Unknown |

Never assign `High` Confidence from weak or missing Evidence.

## Attribution Types

`Self`
: The user's side had a defined responsibility and failed it.

`Other Owner`
: Another owner had a defined responsibility and failed it.

`Upstream Dependency`
: Required upstream input, service, data, permission, or decision was absent, wrong, late, or changed.

`Process / Contract Gap`
: The system allowed ambiguity: no owner, no acceptance criteria, no review gate, no escalation path, or conflicting instructions.

`Environment / External`
: The issue materially depended on runtime, network, third-party service, platform policy, market, hardware, or other uncontrollable condition.

`Requester / Scope Drift`
: The requester's later judgment used requirements that were not agreed before execution.

`Evidence Gap`
: The available Evidence does not support safe attribution.

## Confidence Labels

- `High`: direct Evidence plus clear contract and causal link.
- `Medium`: good Evidence but some missing contract or causality detail.
- `Low`: plausible attribution but Evidence is weak or incomplete.
- `Unknown`: attribution would be speculative.

## Red Lines

- Do not infer motive.
- Do not use "everyone knows" as Evidence.
- Do not treat silence as approval unless the contract says silence means approval.
- Do not blame an owner for missing information they were never required to provide.
- Do not hide self-side responsibility; downgrade the communication instead.
