# Agent delegation

Use independent agents when their contribution justifies the context, token, and coordination costs.

## When to delegate
- The coordinator may choose delegation without separate approval within the authorized task. Delegation does not expand authorization: discussion and review remain read-only, and consequential actions still follow the scope rules.
- Delegate substantial, independent investigation, implementation, or review when it materially improves speed or quality. Keep small tasks and dependent steps together.
- Useful divisions include separate bug hypotheses, independent modules, distinct architectural risks, or an independent review after implementation.
- Do not impose a planner, worker, and reviewer pipeline on every task. Avoid duplicate investigation unless independent confirmation addresses a meaningful risk.
- Start with up to two concurrent subagents. Increase only when more independent work justifies the overhead and the harness permits it. This is a working default, not a configuration change.
- The coordinator owns task division, decisions, conflict resolution, integration, and final verification. Subagents should return to the coordinator rather than delegate further unless explicitly assigned that responsibility.

## Focused inputs
- Give each agent the minimum sufficient context, including consequential constraints. Do not omit necessary information to meet an arbitrary word limit.
- Prefer paths, symbols, and targeted references to copied files or full conversation history. Agents should inspect actual sources themselves.
- Define a bounded objective, relevant entry points, and an expected result. Identify dependencies that must be resolved before work begins.
- Supply a focused context packet: starting paths and symbols, relevant contracts, confirmed findings with source references, and verification commands. Include the relevant diff for follow-up work or review instead of copying the full conversation.
- Use this handoff format, omitting fields that do not apply:

```text
Objective: Specific question or change.
Scope: Relevant files, symbols, or entry points.
Constraints: Required behavior and important decisions.
Known: Confirmed findings and source references; claims to recheck.
Ownership: Read-only, or files this agent may edit.
Checks: Relevant verification commands.
Return: Expected result and verification evidence.
```

## Progressive exploration and reuse
- Do not perform a repository-wide survey at the start of every assignment. Start from supplied entry points, search narrowly, and inspect relevant sections before expanding to direct dependencies.
- Broaden exploration only to answer a concrete unresolved question, such as locating a caller, checking a shared contract, or tracing a failure. State the question and why broader inspection is needed; routine read expansion within the authorized task does not need separate approval.
- Read scope is distinct from write ownership. Inspect relevant shared types, callers, tests, and cross-module contracts when necessary; permission to read a file does not grant permission to edit it.
- Reuse confirmed findings and source locations rather than repeating discovery. Verify claims that affect the current change against current sources; do not treat a prior summary as proof.
- Reuse an existing agent for related follow-up work when the harness supports it and its context remains useful. Give it the new diff, changed constraints, and specific next objective. Start fresh when the role, scope, or accumulated context would make reuse unreliable.
- For follow-up fixes and reviews, inspect the new diff and affected dependencies rather than restarting discovery. Expand when the change invalidates prior evidence or reveals a new risk.
- Give reviewers the diff, acceptance criteria, and relevant execution paths. Require independent inspection of actual code; worker summaries guide navigation without replacing evidence.
- Return useful paths and symbols with findings so later agents have precise starting points. Avoid arbitrary file-count limits that could hide relevant integration behavior.
- When repeated discovery warrants it, maintain a concise project map in existing project documentation: module ownership, entry points, shared contracts, and verification commands. Create or update it only within authorized write scope; avoid speculative maps and full file inventories. The coordinator owns shared map updates, verifies relevant entries before use, and updates entries invalidated by authorized changes.

## File ownership and coordination
- Prefer read-only exploration and review when starting a delegation workflow.
- Give parallel writers exclusive file ownership. Coordinate shared interfaces and contracts before implementation; do not let agents edit the same files concurrently.
- Use separate worktrees when independent changes need isolation. They do not replace agreement on interfaces or integration checks.
- If a worker needs to cross its assigned boundary, it should report the dependency and let the coordinator reassign ownership or perform the shared edit.
- Stop or redirect redundant work once evidence resolves the question. Reuse relevant findings rather than repeating searches.

## Compact outputs
- Return concise findings with evidence, not raw tool logs or a chronological narrative. Include more detail when needed to reproduce a failure or assess a consequential decision.
- Use this result format, omitting empty fields:

```text
Result: Finding or completed change.
Evidence: File references, reproduction, or checks run.
Uncertainty: Assumptions, conflicts, or incomplete checks.
```

- Workers also list changed paths and explain material behavior changes. Report failed, skipped, and unrun checks.
- Reviewers return actionable findings ordered by severity, with affected locations and consequences. Say when no findings were identified; avoid generic advice to fill space.
- Keep large artifacts in files and return their paths with a short explanation. Preserve critical evidence in the summary.

## Integration and completion
- The coordinator inspects delegated results, reconciles disagreements against evidence, and verifies the combined change with appropriate checks.
- Distinguish subagent reports from independently verified outcomes. Do not claim integration succeeded solely because individual workers completed their tasks.
- Consolidate results into one user-facing answer covering the outcome, verification, and unresolved issues.
