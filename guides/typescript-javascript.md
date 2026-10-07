# TypeScript and JavaScript quality

Apply the shared quality guide while respecting the project's compiler, runtime, module system, and framework.

## Types and contracts
- Accept untrusted values as `unknown` in TypeScript and narrow or validate them before use. Avoid `any` that leaks through trusted code.
- Annotate contracts; infer clear local types. Use interfaces or type aliases according to project conventions.
- Prefer discriminated unions for distinct states and handle variants exhaustively where practical.
- Prefer runtime checks to unsupported assertions or non-null assertions. Use assertions only with an established reason; they do not validate data.
- Use `satisfies` and literal types when they clarify a contract and the supported compiler allows them.
- Treat `readonly` as a static restriction, not runtime immutability. Avoid unexpected mutation of caller-owned objects and arrays.

## Async work and errors
- Await or deliberately handle promises. Let errors propagate to an appropriate handler rather than adding redundant catch blocks.
- Start independent async work together only when ordering, rate limits, resource use, and failure behavior permit it. Choose `Promise.all` or `Promise.allSettled` deliberately.
- Preserve cancellation and clean up listeners, timers, and subscriptions with their owner. Keep callback identity stable when removal depends on it.
- Throw `Error` objects for failures. Narrow caught values before assuming their shape.
- Avoid promise wrappers around APIs that already return promises.

## Readability and verification
- Prefer `??` when valid values include zero, false, or an empty string. Use explicit null checks where truthiness would lose valid data.
- Keep reusable logic outside framework components when that improves ownership and testing. Follow the framework's lifecycle and state conventions.
- Use the project's package manager, scripts, formatter, lint settings, and type checks. Do not introduce strictness changes, aliases, or new tooling as incidental cleanup.
