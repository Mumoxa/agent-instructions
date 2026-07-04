# Mumoxa Agent Instructions

This repository is the single source of truth for all Mumoxa coding-agent instructions, playbooks, standards, roles, prompts, UI rules, QA rules, research rules and handoff rules.

Every AI coding agent working in any Mumoxa GitHub repository must follow this file before changing code. Product repos may add repo-specific rules, but they must not weaken these canonical rules.

## Rule zero

No hallucination. No invented facts. No duplicated work. No unsupported verification claims. Evidence first, then action.

This means:

- Do not invent product requirements, architecture, data models, features, user flows, credentials, integrations, test results, build results, security status, performance claims or deployment status.
- Do not claim a command passed unless it was actually run and the output proves it.
- Do not claim a file, component, route, table, API, database, deployment, issue or PR exists unless it was inspected.
- Do not duplicate existing code, utilities, schemas, components, routes, prompts, data models or documentation without first searching for existing work.
- If the evidence is incomplete, say exactly what is known, unknown and assumed.

## Canonical repository rule

The canonical instruction source is:

`Mumoxa/agent-instructions/AGENTS.md`

Do not use `Mumoxa/ai-agent-squad` as the canonical source for agent instructions.

`Mumoxa/Agent-OS` is not canonical unless a user explicitly asks for historical Agent-OS work. Shared agent standards, playbooks, role definitions and operating rules belong here.

## Required reading order for every coding agent

For every task in any Mumoxa repo:

1. Read the target repo's root `AGENTS.md`.
2. Read this canonical file: `Mumoxa/agent-instructions/AGENTS.md`.
3. Read `COMPREHENSIVE_INSTRUCTIONS.md` in this repo when the work is non-trivial, cross-functional, production-facing, security-sensitive, AI-related, assessment-related, recruitment-related, architecture-related or UI-related.
4. Inspect the target repo before editing.
5. Identify the actual stack, package manager, framework, routes, components, styling, database/schema files, API boundaries, tests, deployment config and existing conventions.
6. Search for duplicate or related functionality before adding anything new.
7. Make the smallest safe change that satisfies the user request.
8. Verify the change with available lint, tests, type checks and build checks.
9. Finish with an evidence-backed handoff.

## Standard task workflow

Every agent must follow this workflow:

1. Restate the requested outcome in practical terms.
2. Identify affected surfaces: frontend, backend, database, deployment, security, tests, data, docs and user experience.
3. Inspect relevant files before proposing or applying changes.
4. Check for existing implementations, utilities and patterns.
5. Write a brief plan before code changes, unless the task is a tiny single-file fix.
6. Implement small, reviewable changes.
7. Run the most relevant verification commands.
8. Review the diff against the original request.
9. Document what changed, what was verified, what remains risky and what requires manual checking.

## Non-negotiable verification doctrine

Verification is not optional.

Before finishing, agents must try to run the relevant commands available in the repo, such as:

- dependency install check, when needed;
- lint;
- type check;
- unit tests;
- integration tests;
- e2e tests, where available and relevant;
- build;
- migration dry-run or schema validation, where relevant;
- formatting checks;
- security or dependency checks, where available.

If verification cannot run, the handoff must state:

- which command was attempted or considered;
- why it could not run;
- whether this blocks confidence;
- what a human should run next.

Never replace verification with confidence language.

## UI quality rules

All UI work must aim for modern, polished, production-quality output.

Before coding UI:

- Inspect the existing design system, components, routes, styling, tokens and layout conventions.
- Identify the user flow.
- Avoid generic dashboard/card layouts unless explicitly requested.
- Reuse existing components and design patterns before creating new ones.

UI output must include:

- clean spacing;
- strong hierarchy;
- good alignment;
- responsive behaviour;
- accessible contrast;
- semantic HTML;
- keyboard-accessible interactions;
- focus-visible states;
- loading states;
- empty states;
- error states;
- success states;
- sensible microcopy;
- consistent typography;
- reusable components over one-off styling.

Avoid dated-looking UI, cramped layouts, weak typography, random colours, fake interactivity, inaccessible controls and dead screens.

## Backend, data and platform rules

For backend, data, infrastructure and platform work, agents must verify:

- data flow;
- input validation;
- authentication;
- authorization;
- error handling;
- logging;
- observability;
- migration safety;
- rollback risk;
- rate limits;
- external service dependencies;
- secrets handling;
- safe failure modes.

Never fake integrations. Never hardcode secrets. Never log sensitive data. Never pretend a service works without inspecting code, config or runtime evidence.

## Security rules

Security-sensitive work must include a threat-aware check of:

- authentication and authorization boundaries;
- role-based or capability-based access;
- secrets exposure;
- dependency and supply-chain risks;
- injection risks;
- unsafe file handling;
- sensitive data logging;
- rate limiting;
- unsafe defaults;
- privacy and POPIA/GDPR-type exposure where relevant;
- failure modes and escalation paths.

If the task touches user data, candidate data, client data, recruitment data, assessment data or payment/billing data, treat it as sensitive.

## AI, assessment and recruitment product rules

For AI, assessment, matching, scoring, recruitment, career guidance or candidate/client-facing products:

- Protect credibility above speed.
- No fake metrics.
- No fabricated candidate, client, employer, salary, market, skills or career facts.
- No unsupported scoring logic.
- No hidden bias assumptions.
- No black-box claims without explaining what is measured, inferred and unknown.
- Keep assessment logic auditable.
- Keep matching logic explainable.
- Keep candidate data privacy-aware.
- Avoid claims that imply validation unless validation evidence exists.
- Distinguish demo behaviour from production behaviour.

## Architecture rules

For architecture-impacting work:

- Identify the boundary being changed.
- Identify upstream and downstream systems.
- Document data contracts.
- Prefer reversible changes.
- Use ADR-style notes for major decisions.
- Avoid broad rewrites unless specifically requested and justified by evidence.
- Check deployment, rollback, data migration and observability implications.
- Do not introduce new frameworks, vendors or services without explicit justification.

## Documentation rules

Documentation must be accurate, current and useful.

Do not write aspirational docs as if work is complete. Use clear labels:

- Implemented;
- Partially implemented;
- Planned;
- Unknown;
- Needs verification;
- Demo only;
- Production ready only if verified.

Docs must not conceal gaps, risks or missing verification.

## Code review rules

Every code review must check:

- request alignment;
- existing pattern reuse;
- duplication;
- correctness;
- edge cases;
- accessibility for UI;
- security;
- performance;
- data integrity;
- tests;
- build impact;
- migration impact;
- documentation impact;
- whether claims are evidence-backed.

## Required final handoff format

Every agent must finish with:

1. Summary of changes.
2. Files changed.
3. Verification commands run and results.
4. Risks or gaps.
5. Manual or visual checks still needed.
6. Any assumptions made.

If verification was not run, say so plainly.

## Tool-specific expectations

Agents using Claude Code, Codex, Cursor, GitHub Copilot, OpenCode, Gemini, Windsurf, Cline, Cody, Tabnine or similar tools must configure or prompt the tool to read:

1. the target repo's `AGENTS.md`;
2. `Mumoxa/agent-instructions/AGENTS.md`;
3. `Mumoxa/agent-instructions/COMPREHENSIVE_INSTRUCTIONS.md` for non-trivial work.

Do not rely on tools automatically discovering the rules. Put the reading requirement in the task prompt.

## Comprehensive instruction map

The uploaded instruction pack included a large codex-style operating playbook covering:

- 25 universal operating axioms;
- verification doctrine and SDET spine;
- decision hygiene and pre-mortems;
- cognitive bias and behavioural science;
- persuasion, influence and nudging;
- group dynamics and communication psychology;
- founder, CTO, VP, engineering, product, design, data, ML, platform, security, QA, GTM, legal, finance and people roles;
- product management, UX research, design, architecture, data modelling, prompt engineering, agent handoffs, DevOps/SRE, cybersecurity, QA, documentation, code review, incidents and risk;
- communication, meetings, experimentation, hiring, performance, promotion, technical debt, migrations, cost and vendor management;
- shark-tank critical review, red-team thinking, anti-patterns and emerging methodologies;
- multi-tool adapters for AI coding tools.

The full instruction index is maintained in `COMPREHENSIVE_INSTRUCTIONS.md`.

## Update discipline

When these instructions change:

1. Update this file first.
2. Update `COMPREHENSIVE_INSTRUCTIONS.md` if the scope or section map changes.
3. Update target repo pointers only if the canonical path changes.
4. Do not duplicate the same long instruction body across product repos.
5. Keep product repos lightweight and canonical instructions centralized here.
