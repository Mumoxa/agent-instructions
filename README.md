# Mumoxa Agent Instructions

This repository is the canonical instruction home for Mumoxa coding agents and related AI work.

## Start here

1. `AGENTS.md` — enforceable rules every agent must read first.
2. `COMPREHENSIVE_INSTRUCTIONS.md` — full instruction map covering roles, disciplines, verification, UI, QA, architecture, security, research, AI agent handoffs and Mumoxa-specific product rules.

## Canonical rule

Use this repository as the single source of truth:

`Mumoxa/agent-instructions`

Do not use `Mumoxa/ai-agent-squad` as the canonical instruction source.

`Mumoxa/Agent-OS` is no longer canonical for shared agent instructions.

## Standard prompt header for agents

Use this at the start of coding tasks:

```text
Before doing anything, read and follow this repo's AGENTS.md. Then read and follow the canonical Mumoxa instructions in Mumoxa/agent-instructions/AGENTS.md and COMPREHENSIVE_INSTRUCTIONS.md. Do not use Mumoxa/ai-agent-squad as the instruction source. Do not invent anything, do not duplicate existing work, inspect the repo first, verify all claims with evidence, and run the relevant checks before handoff.
```

## Maintenance

Keep shared rules here. Product repos should only contain lightweight `AGENTS.md` files that point back to this repository and add narrow repo-specific instructions where necessary.
