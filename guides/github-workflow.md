# GitHub workflow

Use GitHub for visible tracking and review, with repository plans for execution details.

## Information ownership
| Artifact | Owns |
| --- | --- |
| Project | Priority, status, task level, role, and overview across issues and PRs |
| Issue | Objective, acceptance criteria, scope, and dependencies |
| Repository plan | Architecture decisions, milestone sequence, execution details, and handoff context |
| Pull request | Proposed code, verification evidence, and code-review feedback |
| Milestone | Meaningful delivery checkpoint grouping issues and PRs |

- Link artifacts rather than copying full content. GitHub owns task tracking; the plan owns execution detail. PR feedback stays in the PR; record only consequential decisions in the issue or plan.
- Use one PR per coherent, reviewable change, not per agent. Several agents may contribute to one feature PR; split large work into independently valid PRs where practical.
- Use parent issues and sub-issues for substantial work that benefits from independent assignment. Do not create an issue for every trivial edit or internal agent action.

## Board and metadata
- Start with Backlog, Ready, In progress, In review, and Done. Represent blocking dependencies separately.
- Track level (small, standard, large, critical), role, and task type. Add priority only when useful for competing work.
- Roles are metadata; GitHub assignees must correspond to actual accounts, not temporary subagent instances.
- Ready means scope and acceptance criteria are clear and dependencies permit work. In review means implementation is available for required review. Done means acceptance and delivery requirements are met.
- Do not automatically mark tasks Done because an agent finished or a PR opened. Merge automation must not bypass outstanding acceptance requirements.

## Execution and feedback
- For substantial features, establish the parent issue and linked plan, then assign ready sub-issues to specialists with exclusive file ownership.
- Use draft PRs for work in progress once pushing and PR creation are authorized. Before requesting review, present coherent changes, verification results, and known limitations.
- Small tasks need relevant checks but no mandatory separate reviewer. Standard tasks need independent agent review. Large tasks need human milestone acceptance. Critical tasks need specialist review and explicit human checkpoints. Follow stronger project requirements.
- Read actionable review comments, delegate fixes, rerun affected checks, and explain the follow-up diff. Report conflicts rather than silently accepting incompatible feedback.
- Keep unresolved feedback visible. Do not claim human approval or resolve another person's review thread merely because a fix was attempted; follow the repository's agreed review convention.
- Link related issues from PRs. Use automatic closing links only when merge will actually fulfill the issue's acceptance and delivery requirements.
- Branch protections and CI enforce configured requirements; prompts do not enforce them. Universal required human approval conflicts with skipping human review for small changes, so propose policy deliberately rather than weakening existing protections.

## Authorization and access
- Identify the repository and available authenticated tools before operating. If Project management is unavailable through the connector, use authorized CLI/API access when available or report the limitation. Do not invent synchronization capabilities.
- Read-only inspection is allowed within the task. Issue creation, comments, Project changes, commits pushed to GitHub, and PR creation require authorization covering that repository and those actions. Once provided, continue within scope without asking for each routine update.
- Permission to implement locally does not imply permission to publish. A draft PR is still an external write. Prepare concrete descriptions, plans, and diffs locally before requesting missing authorization.
- Merge, release, destructive operations, and repository-policy changes require their own applicable authorization. Approval of a plan or review comment is not automatic permission to merge.
- Record only verified external updates. If an operation fails, preserve local work and report what remains unsynchronized; do not silently create competing sources of truth.
