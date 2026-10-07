# Code quality

Make code easy to understand, change, and verify without unnecessary machinery.

## Correctness and contracts
- Read the actual code and relevant configuration before changing it. Memory is a clue, not evidence.
- Preserve behavior and compatibility outside the requested change. Respect module ownership and public contracts.
- Validate untrusted input at boundaries. Type annotations and casts do not replace runtime validation.
- Handle failures explicitly. Do not hide them with empty handlers or success-shaped defaults. An intentionally ignored failure needs a clear reason.
- Follow the project's error strategy. Distinguish an expected missing result from a failure.
- Ensure resources are released on success, failure, and cancellation. Keep ownership and lifecycle clear.
- Never weaken assertions, bypass checks, or special-case inputs merely to make verification pass.

## Readability and design defaults
- Minimize the mental effort required to understand code. Prefer clear names, visible dependencies, and straightforward control flow.
- Give functions cohesive responsibilities. Use guard clauses where they reduce nesting. Extract helpers when they name meaningful steps, isolate complexity, or remove useful duplication; call count alone does not decide.
- Prefer cohesive parameter lists. Group values only when they represent a real concept; avoid arbitrary parameter caps and unexplained positional flags.
- Keep side effects explicit. Prefer immutable values and local state where practical. Make shared mutable state and synchronization deliberate.
- Use precise types for contracts. Prefer explicit variants to unrelated optional fields when they describe different states.
- Prefer composition and simple concrete types. Introduce abstractions for demonstrated needs, including testing and external boundaries; avoid speculative flexibility.
- Keep changes focused. Do not expand into unrelated cleanup. Treat file size, nesting, and complexity scores as review signals rather than universal limits.
- Remove obsolete code made unnecessary by the change. Do not add extension points for hypothetical callers.

## Comments and documentation
- Read `~/.codex/guides/writing.md` before writing comments or documentation. Apply its ASD-STE100 principles and follow project conventions.
- Avoid comments that restate code. Explain non-obvious reasons, constraints, workarounds, and invariants where readers need them.
- Document public contracts when signatures cannot explain behavior, side effects, errors, or lifecycle. Follow project documentation requirements.
- Use enough words to be clear; do not force labels or word limits. Update documentation when the change invalidates it.

## Verification
- Use the project's configured formatter, linter, type checker, and tests appropriate to the change. Do not install tools or change versions merely to follow this guide.
- Test observable behavior and meaningful edge cases. Add a regression test for a bug when practical; explain when reproduction or automation is unavailable.
- Use property tests for meaningful invariants when warranted. Consider mutation testing selectively for critical logic; investigate survivors rather than assuming each is a missing test.
- Keep tests reproducible and isolate state. For randomized failures, preserve a reproducing seed or example.
- If a test or specification appears wrong, explain the conflict. Change expectations only when the requested behavior supports it.
- Report failed, skipped, and unrun checks. Distinguish verified outcomes from assumptions.
