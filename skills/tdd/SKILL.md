---
name: tdd
description: Build testable behavior changes through failing-test, passing-implementation, and refactoring cycles; assess behavior-test quality during assigned QA. Use for test-first features and bug fixes, not routine documentation, configuration, or visual exploration.
---

# Test-driven development

Implementation agents own tests and production code for their assigned behavior. QA independently checks acceptance and test quality; it need not precede every implementation or write every test. Use existing project tools and respect assigned ownership.

## Choose the behavior boundary

Identify the observable behavior and the interface used to exercise it: a function, service, API, component, or other meaningful boundary. Choose the narrowest reliable check that covers the requirement, not automatically an end-to-end test. Follow existing tests and project contracts.

Use acceptance criteria and authorized scope to select boundaries without repeated user confirmation. Ask when required behavior or a consequential contract is unclear. Record consequential coverage decisions in the existing task or plan; keep small-task decisions in chat.

Prioritize core behavior, meaningful failures, and likely regressions. Include high-impact cases such as authorization, data loss, or duplicate execution when relevant. Do not let a small happy-path test stand in for risk-based coverage.

## Implement one behavior at a time

1. Write a focused test with an expected result derived independently from requirements, a known example, or a relevant invariant.
2. Run it and observe failure for the intended missing or incorrect behavior. A syntax error, unavailable dependency, or broken fixture is not evidence of that failure; resolve the test setup first.
3. Implement enough to satisfy this behavior within the task's scope, then run the check to establish that it passes.
4. Make useful small refactors while keeping affected tests green. Repeat for the next behavior; do not batch an imagined full suite before discovering the implementation.

For bug fixes, demonstrate the regression against the unfixed behavior when practical. If test-first execution is unavailable or code already exists, report the actual verification sequence; do not claim TDD without observed red and green evidence.

Run focused checks during the cycle and appropriate integration and required project checks before completion. Add slower browser or device checks when they cover relevant integration or user experience; do not default to them for every cycle. For work without useful independently testable behavior, choose suitable verification instead of manufacturing a test.

## Keep tests worth maintaining

Assert outcomes through relevant interfaces rather than private structure or incidental call order. Tests should survive internal refactors that preserve behavior. Expected results must not recompute the implementation's algorithm or mirror its constants without an independent basis.

Prefer exercising real internal code. Substitute external services, time, randomness, or costly resources when isolation is needed; use existing test infrastructure. Internal mocks or direct persistence assertions need justification tied to the contract or testing constraints, not an absolute ban. Do not weaken assertions to make a failing implementation pass.

## QA and handoff

QA checks actual behavior against acceptance criteria and looks for important omissions, fragile tests, and misleading success. It may add tests only in assigned writable paths; production fixes return to the orchestrator. A retrospective review cannot establish red-before-green from final passing tests alone.

Return brief evidence: behavior exercised, commands and outcomes, relevant paths, observed red/green sequence where available, and remaining gaps. Summarize logs. Keep QA test-file ownership separate from concurrent implementation ownership.

Workflow inspiration: Matt Pocock's TDD skill. This local procedure retains refactoring and selects test boundaries within authorized work rather than requiring confirmation for each boundary.
