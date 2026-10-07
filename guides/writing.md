# Commit messages, comments, and documentation

Write text that helps a reader understand the change, use the software, or maintain the code. Explicit task instructions and repository conventions take precedence.

## ASD-STE100 Simplified Technical English

Use ASD-STE100 principles for English technical prose. This guide adapts those principles for software work; it does not replace the complete standard or its controlled dictionary.

- Write short, clear sentences with explicit subjects and actions. Use active voice when it makes responsibility clear.
- Use direct commands for instructions. Put prerequisites before actions and steps in execution order.
- Use one term for one concept. Explain unfamiliar terms at first use.
- Preserve exact identifiers, commands, paths, UI labels, and domain terms. Format code references as code.
- Avoid idioms, ambiguous pronouns, unnecessary words, and contractions. Do not omit necessary words to shorten sentences.
- Keep each paragraph about one topic. Use numbered lists for steps and bullets for parallel items.
- Make conditions and results explicit. Distinguish required actions from optional actions.
- When strict compliance is requested, check the applicable standard and dictionary, including technical name and verb rules. State what remains unverified.

Reference: [Official ASD-STE100 standard, Issue 9](https://www.asd-ste100.org/assets/files/ASD-STE100_ISSUE9.pdf) and [official FAQ](https://www.asd-ste100.org/STE_faq.html).

## Commit messages

- Inspect the staged diff. Describe the actual change and its purpose.
- Follow the repository format, including Conventional Commits, issue references, and required trailers when applicable.
- Otherwise, use a short imperative subject with a concrete verb, such as `Fix token refresh after session expiry`. Omit the final period.
- Aim for 50 characters in the subject and stay under 72 where practical. Preserve meaning over an arbitrary limit.
- Add a body when needed to explain the reason, behavior change, compatibility impact, or tradeoff. Separate it from the subject with a blank line.
- Explain why the change is needed. Avoid a file-by-file narrative or a copy of the diff.
- Identify breaking changes and migration actions when relevant. Include only supported issue references and trailers.
- Report verification accurately. Do not claim checks, approvals, or results without evidence.
- Keep each commit about a coherent change. Writing a message does not authorize committing, rewriting history, or pushing.

## Code comments

- Prefer clear names and straightforward code. Comment when a necessary reason or constraint is not clear from the code.
- Explain non-obvious decisions, invariants, external requirements, concurrency assumptions, and workarounds. Do not restate code.
- Put comments beside the relevant code. Update them with behavior changes and remove obsolete comments.
- Explain why a workaround is needed and when it can be removed. Link a relevant issue or specification when available.
- Use TODO comments for concrete deferred work. State the missing behavior and a useful issue reference or removal condition.
- Follow project docstring and API comment conventions. Document behavior, input constraints, side effects, errors, and lifecycle where signatures are insufficient.
- Do not retain dead code in comments or add decorative banners and history that version control already records.

## Documentation

- Write for the intended reader and task. Put the purpose, prerequisites, and usable instructions before implementation details.
- Update affected setup, configuration, contract, and migration documentation with behavior changes.
- Describe supported behavior. Distinguish confirmed facts, assumptions, proposals, and limitations.
- Match examples to supported versions and actual interfaces. Use safe placeholders instead of credentials or private data.
- For procedures, state starting conditions, ordered actions, expected results, and relevant recovery steps. Explain destructive effects before the action.
- Document important defaults, units, valid values, failure behavior, and compatibility constraints where needed.
- Keep one authoritative explanation for each topic. Link to it instead of copying instructions.
- Verify changed links, paths, commands, and examples where practical. Run configured documentation checks when available and report unverified items.
- Keep documentation proportional to the change. Avoid speculative features and descriptions that merely repeat code.
