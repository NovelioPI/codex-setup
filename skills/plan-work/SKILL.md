---
name: plan-work
description: Clarify and plan substantial coding work into written milestones, bounded agent tasks, and acceptance checks. Use for implementation planning or requests to grill or stress-test a software idea; skip routine small edits and code-review-only requests.
---

# Plan work

Turn the user's intended outcome into a grounded, executable plan, with questioning proportional to consequential uncertainty.

## Establish scope and authority
- Read applicable project instructions and `~/.codex/guides/agentic-workflow.md`. Use its task types, levels, roles, and review checkpoints; do not duplicate their definitions.
- Inspect relevant entry points and project configuration with targeted searches. Read `~/.codex/guides/delegation.md` before delegating substantial independent investigation. Do not require an explorer or a subagent for every factual lookup.
- Read `~/.codex/guides/github-workflow.md` only when GitHub tracking is relevant. Read relevant quality guides only when a proposed design needs their guidance.
- If a personal reference is unavailable, report that limitation and use available project guidance; do not claim to have loaded it.
- Planning does not authorize implementation or external writes. Brainstorming stays in chat. A request to write a plan authorizes that local artifact; broader implementation authorization may include its necessary plan. Respect separately required checkpoints.

## Clarify through dependency-aware questions
- Separate facts to investigate from decisions requiring user judgment. Find facts in code, configuration, or authoritative documentation rather than asking the user to supply discoverable information.
- Start from the intended user or system behavior, non-goals, and observable acceptance criteria. Map consequential decisions and their prerequisites internally; do not generate an exhaustive tree of hypothetical extensions.
- Skip interviewing for clear small tasks. Clarify consequential gaps briefly for standard work. For large or critical work, examine relevant boundaries, failures, compatibility, sensitive behavior, rollout, and recovery in greater depth.
- An explicit "grill me" request selects deeper questioning, even for a bounded idea, while preserving its scope.
- Ask one consequential question at a time, or a small round of at most three independent questions. Give a recommended answer with its meaningful tradeoff. Wait for actual answers; do not treat silence as confirmation.
- Ask downstream questions only after their prerequisites settle. Incorporate each answer, avoid repeating settled questions, and challenge weak choices with evidence rather than invented objections.
- Continue useful independent research while awaiting answers. Delegate only when the investigation justifies its overhead; provide focused sources and the specific blocked decision.
- Stop when the outcome, boundaries, consequential decisions, and acceptance checks are clear enough to plan. Convert remaining non-blocking unknowns into explicit research tasks, assumptions to verify, or milestone checks.
- After deep grilling, summarize decisions and remaining assumptions and obtain confirmation of shared understanding before finalizing the plan. This confirms understanding; it is not permission to implement, publish, or merge. Clearly label an interim draft if the user requests one before confirmation.

## Write the plan when authorized
- Use the project's planning location or `docs/plans/<change-name>.md`. Adapt [references/plan-template.md](references/plan-template.md) when writing a substantial plan; omit irrelevant sections and avoid empty scaffolding.
- Define milestones as demonstrable outcomes, not merely completed agent activities. Assign bounded tasks with roles, file ownership, dependencies, acceptance checks, and evidence expectations.
- Include independent review and human checkpoints appropriate to the level. Agree shared interfaces before parallel writers start. Do not force each task into one session, one commit, or separate test and implementation agents.
- Keep one authoritative plan and update it rather than creating competing versions. With GitHub, link issues for authoritative status and dependencies instead of duplicating a board locally. Propose issue content locally when external writes are not authorized.
- Check that dependency order is coherent, ownership does not overlap for parallel work, acceptance is observable, and consequential decisions are resolved or explicitly gated.
- End with the level, plan location or chat proposal, key decisions, remaining blockers, and what is ready next. For a planning-only request, stop after planning.
