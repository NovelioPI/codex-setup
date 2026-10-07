# Python quality

Apply the shared quality guide using Python conventions; default to Python 3.12+ unless the project specifies otherwise.

## Types and data
- Prefer built-in generics, `X | None`, and Python 3.12 type parameter syntax where compatible with project tooling. Do not rewrite existing typing solely for style.
- Annotate public contracts and ambiguous boundaries; let clear local values speak for themselves.
- Limit `Any` to genuinely dynamic boundaries. Validate external data before treating it as a trusted type. `cast()` and `TypedDict` perform no runtime validation.
- Use dataclasses for named data with meaningful fields; prefer frozen value objects when practical. Use `TypedDict` for dictionary-shaped contracts and `Protocol` for useful structural interfaces.
- Use literal unions or enums for a fixed set of domain values when they clarify a contract.

## Control flow and resources
- Raise appropriate exceptions for invalid input; do not rely on `assert` for checks that must survive optimized execution.
- Catch specific exceptions where recovery, translation, or useful context is possible. Keep protected operations narrow and preserve exception causes when translating errors.
- Use context managers for resources that support them. Use `ExitStack` for dynamic resource scopes when useful.
- Keep blocking work out of async execution paths. Preserve cancellation and make background task ownership explicit.
- Use comprehensions for readable collection construction, loops for side effects, and generators for streaming or unbounded input.
- Avoid mutable default arguments, hidden shared state, and caching functions whose results depend on untracked mutable state or side effects.

## Interfaces and verification
- Use the project's logger in reusable application or library code; reserve direct output for deliberate CLI or script behavior.
- Prefer explicit imports and private names for implementation details. Preserve metadata when writing decorators.
- Use configured project checks. If Ruff, a type checker, pytest, or property-testing tools are already configured, follow their existing settings and commands.
