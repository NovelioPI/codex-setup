# Mobile design and verification

Use the shared brief and inspiration workflow for mobile UI, adapting decisions to the supported platforms and the existing app. Consult current official platform guidance when specific platform requirements matter; do not impose one fixed mobile style across projects.

## Design for the app and platform

Inspect the relevant screens, shared widgets or composables, theme tokens, navigation, and state conventions. Reuse the existing foundation. For Kotlin or Flutter, choose guidance for the project's actual UI toolkit and target platforms; do not assume every Kotlin app uses Compose or every Flutter app targets only Android.

Choose navigation, back behavior, controls, and gestures that fit the platform and primary user actions. Consider safe areas, system bars, keyboard obstruction, text scaling, screen-reader semantics, touch access, and supported screen sizes. Apply orientation, tablets, or other device variations only when in scope.

Design permission, loading, empty, error, and offline states when relevant. Explain recovery and avoid losing user input unnecessarily. Consider app backgrounding and return behavior when the feature depends on it. Keep proposed UI behavior aligned with the existing lifecycle and data architecture.

## Verify on the relevant surface

Use the project's existing checks and available device or emulator tools. Exercise the changed flow and relevant states; inspect rendered screenshots for layout and visual consistency. Preview or widget tests provide useful evidence but do not prove all device behavior.

Report the platform and environment exercised and any unavailable verification. Use browser tools for browser surfaces only; browser success does not establish that native navigation, permissions, lifecycle, or rendering works. Do not install extra tooling or create a separate verification harness by default.
