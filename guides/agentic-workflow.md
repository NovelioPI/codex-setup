# Agentic workflow

Coordinate specialists through written outcomes, bounded tasks, and proportionate review.

## Classification
- Classify by task type and handling level. Use the highest applicable level; file count and line count alone do not decide. Explain the classification briefly when it affects planning or review.
- Research answers a bounded question with evidence. Bugs establish cause and verify a fix. Features define observable acceptance behavior. Refactors identify behavior to preserve. Migrations address compatibility, rollout, and recovery. Reviews report evidence-backed findings.

| Level | Characteristics | Planning | Review |
| --- | --- | --- | --- |
| Small | Clear, local, low risk | Chat, or an entry in an existing plan | Relevant checks; no mandatory separate reviewer or human checkpoint |
| Standard | Bounded feature or meaningful behavior change | Concise written tasks and acceptance checks | Independent agent review before completion; human review available |
| Large | Several components, dependencies, significant uncertainty, or multiple sessions | Written milestones and assigned tasks | Independent review and human acceptance at milestone boundaries |
| Critical | Security-sensitive behavior, sensitive data, irreversible migration, or consequential compatibility change | Written risks, compatibility, rollout, and recovery | Relevant specialist review and explicit human checkpoint before consequential implementation or delivery |

- A small change in permissions or authentication can be critical. Increase the level when new evidence warrants it; do not silently downgrade required review.
- A written plan does not by itself require separate approval for ordinary work already authorized. Ask about consequential uncertainties and pause at the required human checkpoints.
- During discussion or read-only review, propose plans in chat; write files only when authorized. Honor a project's stronger review requirements.

## Written plan
- Use the project's existing planning location or `docs/plans/<change-name>.md`. Begin with one plan per substantial change; separate a detailed specification only when it adds value.
- Record objective, non-goals, constraints, consequential decisions and reasons, milestones, tasks, verification evidence, and unresolved issues. Link existing information instead of duplicating it.
- A milestone is an observable outcome that can be demonstrated. A task is a bounded contribution to that outcome, assigned to an agent role.
- Each task records its ID, expected outcome, role, file ownership, dependencies, acceptance checks, status, and evidence. Use a table for the task overview and short details only where needed.
- The orchestrator owns shared plan updates. Workers return findings and changed paths; do not have parallel workers edit the plan.
- Update at meaningful task or milestone transitions and before handoff, not after every tool call. Read only relevant milestones and shared constraints when dispatching work.
- When using GitHub, issue status and dependencies are authoritative for tracking. The plan links issue IDs and preserves execution detail; do not maintain a competing status board.

## Roles and dispatch
| Role | Responsibility |
| --- | --- |
| Main session: orchestrator | Classify, plan, agree contracts, assign ready work, integrate, verify, and manage user feedback |
| Backend | APIs, domain logic, persistence, and integrations; include relevant tests |
| Frontend | Web interaction, accessibility, UI, and client state; include relevant tests |
| Mobile | Kotlin or Flutter app behavior, lifecycle, and platform integration; include relevant tests |
| Researcher | Resolve unknown APIs, feasibility, framework behavior, or diagnostic hypotheses with evidence |
| QA | Check acceptance behavior, edge cases, regressions, and integration; add tests only in assigned scope |
| Reviewer | Independently inspect correctness, maintainability, regressions, and contracts; return findings without rewriting code |
| Security reviewer | Assess relevant trust boundaries, permissions, sensitive data, and abuse cases for consequential risks |

- Agents inspect relevant sources themselves. Do not require an explorer stage or run every role on every task.
- Use custom agents in `~/.codex/agents/` when available; otherwise dispatch the same bounded role instructions through the harness's available agent tools. Do not claim custom-role loading was verified merely because files exist.
- Delegate substantial specialist implementation. The main session may handle small tasks, shared integration edits, and straightforward fixes directly.
- Dispatch only tasks whose dependencies are satisfied. Agree shared contracts before parallel implementation and give writers exclusive ownership. Follow the delegation guide for handoffs and concurrency.
- QA supplements worker verification. Reviewers should be separate from the author; reviewing only the worker's summary is insufficient.

## Verification and human review
- Inspect worker changes, run appropriate combined checks, and obtain required independent review. Fix meaningful findings and verify affected behavior before presenting readiness.
- Pause at large-work milestone boundaries for human acceptance before continuing to the next milestone, unless the user explicitly changes that checkpoint policy. Critical work also needs the relevant pre-action checkpoint.
- Present observable behavior, changed paths or diff, demo instructions, checks actually run, known limitations, and decisions requiring judgment.
- Distinguish implementation complete, verified, ready for human review, accepted, and delivered. Worker completion is not milestone acceptance.
- Record actionable feedback with open, addressed, or needs-clarification status in the plan, or in the PR when GitHub is used. Delegate corrections, rerun affected checks, and present the follow-up change.
- Feedback that changes scope or acceptance criteria updates the authoritative issue or plan. Do not treat discussion comments as blanket authorization for unrelated changes.
