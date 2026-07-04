# Mumoxa Agent Instructions

This repository is the single source of truth for all Mumoxa coding-agent instructions, playbooks, standards, roles, prompts, UI rules, QA rules, research rules and handoff rules.

Every AI coding agent working in any Mumoxa GitHub repository must follow these rules before changing code.

## Rule zero

No hallucination. No invented facts. No duplicated work. No unsupported verification claims. Evidence first, then action.

## Mandatory operating rules

1. Read this file before doing any work.
2. Read the target repository's own `AGENTS.md` before editing.
3. Treat this repository, `Mumoxa/agent-instructions`, as the canonical instruction home.
4. Do not use `Mumoxa/ai-agent-squad` as the canonical source for agent instructions.
5. Do not invent product requirements, architecture, data models, features, user flows, credentials, integrations, test results, build results, security status, performance claims or deployment status.
6. Source-verify every material claim. If the repo, issue, file, log, test, build output, user instruction or cited source does not prove it, say it is unknown.
7. Before coding, inspect the existing repo structure, package manager, framework, routes, components, database/schema files, API boundaries, tests, deployment config and styling conventions.
8. Before making product/UI changes, produce a brief implementation plan and check for duplication against existing components, pages, routes, schemas and utilities.
9. Prefer small, reviewable patches. Avoid broad rewrites unless the user explicitly requested them and the evidence supports it.
10. Reuse existing components, utilities, schemas and design-system patterns before adding new ones.
11. Run the relevant lint, tests, type checks and build commands when available. If they cannot run, document the exact reason.
12. Finish with a concise handoff: what changed, files touched, verification run, risks, gaps and what should be visually or manually checked.

## Required workflow for every task

1. Restate the requested outcome in practical terms.
2. Inspect the repo before editing.
3. Identify affected frontend, backend, database, deployment, security and test surfaces.
4. Check whether similar functionality already exists.
5. Make the smallest safe change.
6. Verify with commands or explain why verification was not possible.
7. Report only evidence-backed results.

## UI standards

When working on UI, produce modern, polished, production-quality interfaces.

Before coding UI:

- Inspect the existing design system, components, routes, styling and layout conventions.
- Identify the user flow and propose a brief UI plan.
- Do not produce generic dashboard/card layouts unless requested.

UI work must include:

- Clean spacing, hierarchy, alignment and responsive behaviour.
- Accessible contrast, semantic HTML and keyboard-accessible interaction states.
- Loading, empty, error and success states where relevant.
- Reusable components over one-off styling.

Avoid dated-looking UI, cramped layouts, weak typography, random colours, dead screens and fake interactivity.

## Backend and data standards

For backend, data and platform work:

- Verify data flow, validation, authentication, authorization, error handling, observability and migration safety.
- Never fake integrations or pretend external services work without proof.
- Never expose secrets or log sensitive data.
- Check rate limits, input validation and safe failure modes.
- Document migrations, schema changes and rollback risks.

## AI, assessment and recruitment standards

For AI, assessment, matching, scoring and recruitment products:

- Protect credibility above speed.
- No fake metrics.
- No fabricated candidate, client, employer, salary or market facts.
- No unsupported scoring logic.
- No hidden bias assumptions.
- Explain what is measured, what is inferred and what is unknown.

## Tool-specific expectation

If using Claude Code, Codex, Cursor, Copilot, OpenCode, Gemini, Windsurf, Cline, Cody, Tabnine or similar tools, configure the tool to read the target repo's `AGENTS.md` first and then this canonical `Mumoxa/agent-instructions/AGENTS.md`.

If there is a conflict, this canonical file takes precedence unless the target repository explicitly documents a narrower project-specific exception.

## Final handoff format

Every agent must finish with:

- Summary of changes.
- Files changed.
- Verification commands run and results.
- Risks or gaps.
- Manual or visual checks still needed.
