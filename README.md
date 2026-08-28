# GrowthOps <sub>(working name)</sub>

A spec-driven growth agent system, being built to run a **real overseas self-serve acquisition funnel** for an ed-tech SaaS — with deterministic guardrails, evals, and ablation-measured iterations.

> **Spec first.** Every iteration starts with a requirements doc; acceptance criteria map 1:1 to eval cases. Code is the validator of requirements.

## Why

Two problems, one system:

- **Business** — a zero-budget SaaS needs its first overseas users: landing → signup → activation, owned end to end.
- **System** — LLMs multiply content throughput, but probabilistic output conflicts with a zero-incident bar for outbound content.

GrowthOps answers both: **agents for throughput, engineering for determinism, a real funnel for proof.**

## Principles

1. **Agents propose; the pipeline disposes.** Probability is confined to the proposal stage.
2. **Spec first** — REQ before code; AC ↔ eval cases 1:1.
3. **Memory is governed, not accumulated** — writes require approval; insights carry source / confidence / date.
4. **Honest small samples** — *n* is always disclosed.
5. **Failures are assets** — the experiment ledger prevents repeat proposals.

## Architecture (4 modules)

**Agent** (weekly-loop state machine: Plan → Draft → Check → human gate → Execute → Measure → Learn) · **Skills** (copy-draft / cultural-check / experiment-design / funnel-analysis, each = prompt + schema + validator + golden tests) · **MCP** (analytics & email connectors — the agent process holds no send credentials) · **Memory** (experiment ledger; market insights with source / confidence / date).

## Roadmap = ablation

Every module added must earn a before/after number.

| version | adds | measures |
|---|---|---|
| v0.1 | manual baseline funnel (no AI) | business baseline + human timing (the denominator) |
| v0.2 | copy-draft skill + output contracts + deterministic checks | no-edit acceptance rate; time per email vs human |
| v0.3 | experiment-design skill + ledger memory | repeat-proposal rate ↓ |
| v0.4 | analytics MCP loop + hardened cultural checks | report citation error rate; checks triggered |
| v0.5 | memory-informed planning + **agent-vs-human copy A/B** | real open/click deltas (*n* disclosed) |

## Docs

Primary docs are in Chinese — this README is the English entry point.

```
prd/            product requirements (v0.x)
requirements/   per-iteration REQs (AC ↔ EV mapping)
experiments/    pre-registered experiment specs
adr/            architecture decision records
evals/          eval evolution & regression assets
```

**Status:** v0.1 (manual baseline) — in progress. **License:** TBD.
