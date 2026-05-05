# Token Gate

Token Gate is a silent pre-execution skill for Codex-style coding agents.

It prevents avoidable model-context waste before expensive work starts, while preserving the user's original goal, deliverable, quality standard, and acceptance criteria.

## Why It Matters

Large token usage is sometimes necessary. Full audits, complete artifact generation, compliance work, and exhaustive reviews may legitimately need a large context budget.

Token Gate focuses only on meaningless token consumption: full-repository reads when an index is enough, full-log ingestion when filtered traces are enough, raw CSV/JSON/PDF loading when schema and samples are enough, or large chat output when a file artifact is the right delivery surface.

## Innovation Points

- Goal-preserving interruption: the skill only pauses when the same final outcome can be reached through a better path.
- Meaningless-cost distinction: it separates justified high token use from avoidable waste.
- Four-level gate: high-risk detection, avoidability, equivalent path, and interruption value must all pass.
- Path-constraint awareness: suggested paths, default paths, and hard constraints are handled differently.
- Deterministic preprocessing bias: indexing, filtering, sampling, diffing, and extraction happen before model-context spending.
- Silent default: normal tasks proceed without token-cost commentary.
- Acceptance-criteria firewall: cheaper paths are rejected if they weaken correctness, completeness, auditability, or output quality.

## Recommended Use

Install Token Gate globally when agents frequently handle:

- repository or multi-file analysis
- large logs and stack traces
- CSV, JSON, XML, PDF, or OCR workflows
- large generated artifacts
- repeated context across turns
- subagent-heavy planning or review
- debugging based on diffs, changed files, entrypoints, or failing traces

## Not Recommended

Do not use Token Gate to shrink the user's goal or avoid necessary work.

Do not interrupt when the user explicitly requests exhaustive review, complete documentation, line-by-line analysis, compliance-grade audit, or full artifact generation.

Do not use it when the alternative path is speculative, marginally cheaper, or less auditable.

## Installation

Copy the `token-gate` directory into your Codex skills directory:

```bash
mkdir -p "$CODEX_HOME/skills"
cp -R token-gate "$CODEX_HOME/skills/token-gate"
```

If `CODEX_HOME` is not set, use your local Codex home path, commonly `~/.codex`.

## Files

- `token-gate/SKILL.md`: the skill instructions and decision gate.
- `token-gate/agents/openai.yaml`: UI metadata for the skill.

## License

No open-source license has been selected in this release. Treat the contents as all rights reserved unless the repository owner adds a license.
