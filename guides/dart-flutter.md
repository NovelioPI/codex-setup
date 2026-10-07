# Dart and Flutter quality

Apply the shared quality guide while respecting the project's Dart and Flutter versions and architecture.

## Dart contracts and async work
- Use precise types at boundaries and public declarations; infer clear local values. Contain `dynamic` and validate external data before trusting it.
- Prefer enums or sealed variants for distinct domain states when supported. Handle variants deliberately.
- Prefer final fields and immutable values where practical. Keep equality and hash codes consistent; avoid mutable value-based map keys.
- Use named parameters when they explain call-site meaning. Distinguish ordinary absence from an empty result according to the contract.
- Prefer readable async/await. Await futures or deliberately mark and handle background work; `unawaited` alone does not handle errors.
- Start independent work together when ordering, resource limits, and failure handling allow it.
- Catch errors only where meaningful recovery or reporting is possible. Use `rethrow` when propagating a caught failure to preserve its stack.
- Keep subscriptions, sinks, controllers, and async work tied to an owner that cleans them up.

## Flutter lifecycle and UI
- Keep expensive work and unintended side effects out of `build`. Follow the project's state management and lifecycle conventions.
- Keep business logic outside widgets when it belongs to the domain or data layer.
- Before using a context after an async gap, check the mounted state of the relevant context. Prefer cancellation where it prevents obsolete work.
- Use const widgets when applicable and extract meaningful reusable widget components. Avoid splitting UI solely to reduce line count.
- Use lazy builders for large lists. Keep rebuild scope appropriate to the changed state; measure performance before adding complexity.
- Dispose owned resources and prevent completed async work from updating disposed state. Not every future supports cancellation.

## Verification
- Use configured analyzer, formatter, and test commands. Follow existing lint and dependency choices.
- Test domain behavior separately from widget behavior where practical. Use integration tests for important flows when warranted.
