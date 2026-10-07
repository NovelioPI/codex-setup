# Memory and handoffs

Preserve useful knowledge and unfinished work while keeping context small and verifiable.

## Choose the right home
- Keep personal working preferences in global instructions and guides. Do not change global rules or guides without a separate user request.
- Keep required project conventions in project instructions or maintained documentation. Built-in memory is a helpful recall layer, not the only source of required rules.
- Store project-specific decisions and confirmed lessons in existing relevant documentation where possible. If none fits, use a concise project lessons file in the project's documentation location; follow project conventions rather than imposing a universal path.
- Keep temporary task state in chat for single-session work. Create or update a project handoff only when work spans sessions or continuity needs it, within authorized write scope. For read-only work, provide the handoff in chat unless saving it is requested.
- Treat generated Codex memory files as managed state. Do not hand-edit them as the primary way to enforce preferences or project knowledge.

## Learn from confirmed mistakes
- Reflect after a meaningful failure, user correction, or discovery. Do not create reflection notes for every trivial task.
- Establish the failure and cause from evidence, fix the issue, and verify the behavior before presenting a durable lesson as confirmed.
- Prefer a regression test or automated check that prevents recurrence. Record a lesson only when it provides useful context beyond existing checks or documentation.
- During authorized implementation, recording useful project lessons is allowed without a separate approval. Keep writes focused and mention recorded lessons in the final response. Discussion and review remain read-only.
- Search existing documentation before adding a lesson. Update the relevant entry rather than appending duplicates. Do not create empty lesson files or copy global guidance into every project.
- Use this compact format where useful:

```text
Trigger: Conditions that exposed the problem.
Cause: Confirmed reason it failed.
Prevention: Specific action or check that avoids recurrence.
Evidence: Source paths, reproducing case, or verification.
Scope: Projects, components, or versions where it applies.
```

- Keep project lessons scoped. Do not generalize one project's failure into a universal rule without evidence. Propose recurring workflow lessons for promotion into a guide or skill rather than changing global behavior automatically.
- Do not store secrets or speculation as durable lessons. Keep unresolved hypotheses clearly labeled in task state instead.

## Retrieve and maintain selectively
- Search relevant project documentation when recalled knowledge could affect the task. Read only matching sections; do not load every lesson at startup.
- Verify remembered claims against current code, configuration, or authoritative documentation before relying on them. Explicit instructions and current evidence take precedence.
- Within authorized maintenance or implementation, correct or retire lessons invalidated by the change. Preserve a still-useful explanation of historical decisions when appropriate; avoid unrelated cleanup.
- Memory improves available context; it does not retrain the underlying model. Built-in memory is generated in the background and cannot replace an explicit handoff for reliable resumption.

## Preserve task continuity
- In handoffs and compaction summaries, preserve the objective, constraints, relevant authorization boundaries, decisions and reasons, changed paths and why, current hypothesis, ruled-out causes, pending work, and verification status.
- Keep exact failing check names and the error excerpts needed to reproduce or diagnose the failure. Preserve a reproducing seed or input for randomized failures.
- Clearly separate completed, verified work from assumptions and next steps. For delegated work, preserve ownership and unresolved integration dependencies.
- Link to artifacts rather than copying them. Summarize raw searches, repeated file contents, and passing logs; do not carry their full text forward.
- Reuse and update an existing handoff rather than creating parallel accounts of the same task. Do not treat a handoff as authority to expand scope or perform consequential actions.
