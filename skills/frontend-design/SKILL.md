---
name: frontend-design
description: Develop project-specific web and mobile UI and UX direction through relevant inspiration, reusable components, and visual verification. Use for new interfaces or substantial redesigns; follow existing conventions directly for routine UI edits.
license: Complete terms in LICENSE.txt
---

# Frontend Design

Design around this project's users, content, and primary actions. Use a repeatable decision process, while letting the visual result vary with the brief. User requirements and established project design systems take precedence.

## Establish the brief

Inspect the assigned UI, relevant components, tokens, brand assets, and project conventions before proposing a design. Identify the audience, main user actions, content, device needs, and constraints. Distinguish an application, marketing page, reading experience, or other surface; choose structure for its job rather than assuming a hero or landing-page layout.

Ask only for missing information that materially changes the direction. Recommend a direction when the user has no design expertise; do not require them to choose fonts or supply references. Label assumptions and proposed business content. Do not invent testimonials, product capabilities, or other factual claims.

For routine edits, reuse the existing design without a research or approval ceremony. For substantial new UI or redesigns where the direction is open, read [references/inspiration.md](references/inspiration.md) before selecting the direction. If sufficient inspected references are already available, reuse the relevant findings.

For mobile design, read [references/mobile.md](references/mobile.md). Skip it for web-only work.

## Choose a direction

Connect visual decisions to the brief and inspected references. Consider hierarchy, content density, navigation, typography, colors, spacing, component shapes, and motion as appropriate. Give a compact recommendation with its rationale; for substantial open-ended work, briefly compare one meaningfully different alternative.

There is no globally preferred palette, font, layout, light or dark theme, decorative treatment, or level of boldness. Familiar patterns and system fonts are valid when they fit. Do not ban a style because it is common, or demand novelty where usability benefits from convention. Related products may appropriately share a visual language; unrelated projects should not inherit prior styling without a reason.

For larger work, build one representative screen for user feedback before extending the direction across the application. Follow the orchestrator's review milestones; do not add approval gates to already settled small changes.

## Build a shared foundation

Reuse and extend the project's existing design system and component library. If none exists, establish only the foundation needed now: shared colors, type roles, spacing, and common controls. Use the project's token format and framework; introduce additional tooling or dependencies only within the authorized scope.

Extract components when patterns repeat or need consistent behavior. Keep component APIs clear and bounded. Prefer shared tokens and reusable behavior to duplicated screen-specific styling, while allowing page-specific composition. Avoid a universal component with excessive options or a full component library built speculatively.

## Verify the result

Use real content or clearly identified placeholders. Cover relevant loading, empty, error, and success states. Preserve semantic structure, keyboard access, visible focus, readable contrast, and reduced-motion preferences. Check relevant narrow and wide layouts and the primary user flow.

Use the playwright skill when real-browser checks are appropriate. Inspect rendered screenshots rather than treating a successful build as visual evidence. Confirm that the chosen direction serves this brief and that components and styles reuse the shared foundation. Address observed problems within scope; report unavailable checks honestly.

Return concise design decisions, changed paths, verification evidence, and unresolved issues as relevant. Keep research notes in the existing project plan or design document when useful; do not create a mandatory set of design artifacts.

This is a local adaptation of Anthropic's frontend-design skill. Retain LICENSE.txt; upstream replacement may overwrite these project-independent workflow changes.
