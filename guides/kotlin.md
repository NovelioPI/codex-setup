# Kotlin quality

Apply the shared quality guide while respecting the project's Kotlin version, platform, and framework.

## Types and state
- Prefer `val` and immutable value objects where practical. Read-only collection interfaces do not guarantee that no other reference can mutate the contents.
- Make public contracts explicit. Contain Java platform types at boundaries with deliberate null handling.
- Prefer safe calls, smart casts, and explicit checks to `!!`; use it only with an established invariant.
- Use enums or sealed hierarchies for meaningful variants and exhaustive `when` expressions where appropriate.
- Use data classes for values, and value classes when they enforce a useful domain distinction.
- Keep scope functions brief and their receiver clear. Use loops when a transformation chain hides side effects or control flow.

## Errors, resources, and coroutines
- Use `require` for invalid arguments and `check` for invalid state. Use nullable results or the project's result type for ordinary absence or expected outcomes.
- Catch exceptions where they can be handled meaningfully. Preserve coroutine cancellation; do not swallow `CancellationException` in broad handlers.
- Use `use` for supported closeable resources.
- Launch work in an owned scope with a clear lifetime; avoid `GlobalScope` for ordinary application work.
- Keep blocking work off the main thread. Inject dispatchers or scopes where it improves testing or lifetime control.
- Expose read-only flow contracts when callers should observe rather than mutate state. Make long-running computation responsive to cancellation.

## Boundaries and verification
- Use private or internal visibility for implementation details. Follow project API and documentation requirements.
- Prefer composition to inheritance that breaks a parent contract. Use language features only when compatible with supported versions.
- Use configured Gradle tasks, tests, formatting, and static analysis. Do not impose Android conventions on unrelated Kotlin targets.
