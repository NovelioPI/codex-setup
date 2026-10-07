# Plan template

Adapt this structure to substantial work; replace example text and omit sections that do not apply.

```markdown
# Change name

## Outcome and boundaries
State the observable outcome, task type and level, non-goals, supported versions, and important constraints.

## Approach and decisions
Describe the chosen approach, consequential alternatives, decisions and reasons, and relevant source paths or contracts.

## Milestones
### M1: Observable outcome
Acceptance: behavior or demonstration that proves the milestone works.
Verification: project commands and relevant manual checks.
Review: independent review and any required human checkpoint.

## Tasks
| ID | Outcome | Role | Write ownership | Depends on | Acceptance/check | Status/evidence |
| --- | --- | --- | --- | --- | --- | --- |
| T1 | Bounded contribution to M1 | Relevant specialist | Specific paths | None | Observable check | Pending |

With GitHub tracking, use issue links for task status and dependencies; keep execution-specific detail here instead of duplicating those fields.

## Unknowns and risks
Identify unresolved questions, verification tasks, compatibility risks, and required rollout or recovery steps. Distinguish assumptions from verified facts.

## Progress and review
Record meaningful verified outcomes, unresolved feedback, and next steps. Keep PR feedback in linked PR threads when GitHub is used.
```
