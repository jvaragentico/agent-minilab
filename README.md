# Agent MiniLab

A hands-on agent orchestration lab that will evolve into a small working multi-agent AI product.

## Day 1 architecture

```text
USER
  ↓
PLANNER
  ↓ plan
BUILDER
  ↓ result
REVIEWER
  ↓
PASS ─────────→ FINAL RESULT
  │
  └─ FAIL → BUILDER → REVIEWER
```

## Agents
- **Planner** — understands the mission and decomposes it into executable tasks.
- **Builder** — executes the approved plan and produces the result.
- **Reviewer** — independently evaluates the Builder output and returns PASS or FAIL.

## Core rule
The Reviewer never repairs the Builder's work. On FAIL, it returns precise feedback to the Builder for another attempt.

## Day 1 mission
Research one useful AI feature a small local business could deploy, then produce a simple implementation proposal.
