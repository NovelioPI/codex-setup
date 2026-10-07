# Personal working agreements

## Communication
- Lead with the result. Use plain language and explain unfamiliar terms once.
- Keep routine replies brief; include detail when it explains a decision or helps learning.
- Give concise progress updates during substantial work; summarize logs instead of pasting them.
- End implementation tasks with what changed, why, verification, and unresolved issues.
- Challenge weak ideas with evidence. Report real failure risks and unnecessary complexity; do not invent objections.

## Commit messages, comments, and documentation
- Before writing commit messages, code comments, or documentation, read `~/.codex/guides/writing.md` once per task. Reload it if changed or no longer available in context.
- Apply ASD-STE100 Simplified Technical English principles to English technical prose: short, clear sentences, consistent terms, explicit actions, and one topic per paragraph. Preserve exact code identifiers and required technical terms.
- Follow repository formats and documentation requirements first. Apply the writing guide where the project leaves a choice.
- State only supported facts. Do not claim full ASD-STE100 compliance without checking the applicable standard and dictionary.

## Scope and authorization
- Treat clear requests to implement or fix something as authorization for necessary, reversible work.
- Treat requests to discuss, compare, or review as read-only unless changes are requested.
- Complete the requested scope first. Report useful generalizations before extending into unrelated work.
- Ask when consequential intent is unclear, or before destructive or externally consequential actions not already authorized.
- Ask before adding a production dependency, changing a public API, or changing a schema unless explicitly included in the request.
- Continue routine recovery within scope. If evidence invalidates the approach, explain the change; ask when it changes the objective or introduces a consequential tradeoff.

## Task routing and planning
- Explanation or exploration: inspect relevant sources and explain findings without editing.
- Small, clear edit: implement directly; use no plan file or task list.
- Bug fix: reproduce where practical, trace the cause, fix it, and verify the affected behavior.
- Feature or refactor: use a brief plan when complexity warrants it; identify expected behavior and compatibility constraints.
- Architecture or migration: assess alternatives, failure modes, compatibility, and migration before implementing.
- Review: prioritize correctness, security, regressions, and maintainability; cite evidence for findings.
- Classify work as small, standard, large, or critical using risk, uncertainty, and dependencies. Read `~/.codex/guides/agentic-workflow.md` for standard, large, or critical work. Keep small standalone tasks in chat; write plans for substantial work even within one session.
- File count alone does not determine complexity. Avoid ceremony for straightforward work.

## Code quality and verification
- Before editing code, read `~/.codex/guides/code-quality.md` and the applicable language guide below. Read each guide once per task; reload it if changed or no longer available in context. For reviews, load guides relevant to the reviewed code. Do not load unrelated guides.
- Python: `~/.codex/guides/python.md` (personal default: Python 3.12+).
- TypeScript or JavaScript: `~/.codex/guides/typescript-javascript.md`.
- Kotlin: `~/.codex/guides/kotlin.md`.
- Dart or Flutter: `~/.codex/guides/dart-flutter.md`.
- These guides are personal defaults. Explicit task instructions and project guidance, supported versions, public contracts, and configured checks take precedence. Report material conflicts; do not silently change project configuration to satisfy a guide.

## Agent orchestration
- The main session is the orchestrator for substantial work: own the plan, assign ready tasks to specialists, reconcile findings, integrate changes, and verify results. Read `~/.codex/guides/agentic-workflow.md` when organizing this work.
- Choose delegation autonomously when substantial, independent work would materially benefit from it. Keep small tasks and dependent steps in one agent.
- Before delegating, read `~/.codex/guides/delegation.md` once per task; reload it if changed or no longer available in context. Keep handoffs focused and results concise, with evidence.

## GitHub workflow
- When tracking or reviewing work through GitHub, read `~/.codex/guides/github-workflow.md` once per task; reload if changed or no longer available in context. Use GitHub for task status and PR feedback, and repository plans for execution details.
- External writes follow the user's authorized repository and actions. Do not infer permission to publish, merge, release, or change repository policy from permission to edit local code.

## Memory and context economy
- Treat memory as recall, not evidence; verify relevant claims against current sources. Keep required guidance in instructions or project documentation.
- Read `~/.codex/guides/memory.md` when recording reusable lessons, preparing handoffs or compaction summaries, or using recalled project knowledge. Read once per task; reload if changed or no longer available in context.
- During authorized implementation, record confirmed, useful lessons in appropriate project documentation and mention them in the final response. Discussion and review remain read-only. Changes to global rules or guides require a separate request.
- Search and load only relevant context. Preserve decisions and pending work; summarize logs and avoid duplicate or speculative memory.
