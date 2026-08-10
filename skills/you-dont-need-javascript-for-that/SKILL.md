---
name: you-dont-need-javascript-for-that
description: Audit frontend behavior and replace unnecessary JavaScript with accessible, maintainable native HTML and CSS while retaining minimal JavaScript when requirements demand it. Use for JavaScript-removal requests, native HTML/CSS rewrites, dependency-free UI simplification, or reviews of custom accordions, dialogs, popovers, forms, navigation, responsive behavior, animation, and browser APIs.
---

# You Don't Need JavaScript for That

Prefer the web platform only when it preserves required behavior. Treat fewer moving parts as the goal, not zero JavaScript.

## Workflow

1. **Audit before editing.** Trace the current interaction, state, data flow, keyboard behavior, focus, announcements, validation, failure states, and tests. Record observable behavior that must remain.
2. **Establish constraints.** Find the project's declared browser targets, accessibility standard, design constraints, progressive-enhancement policy, and server-rendering requirements. Do not guess support from feature age.
3. **Map native candidates.** Identify what semantic HTML, native controls, CSS, or browser capabilities can own. Read only the relevant references below.
4. **Choose the smallest safe change.** Preserve the public behavior and remove only the JavaScript made redundant by the native primitive. Prefer progressive enhancement over all-or-nothing rewrites.
5. **Keep necessary JavaScript.** Retain script for dynamic data, application state, cross-field or business validation, analytics, imperative browser APIs, and gaps in required platform support. Explain why each remaining piece belongs.
6. **Verify.** Run focused tests and inspect keyboard operation, focus order/restoration, accessible names and state, zoom/reflow, reduced motion, no-script or failure behavior, and every required browser.

## Decision Rules

- Reject a native replacement that weakens semantics, accessibility, security, required compatibility, or user-visible behavior.
- Do not recreate a native control with generic elements and ARIA. Use native semantics first; use ARIA only to fill a real semantic gap.
- Do not move business logic into CSS or markup merely to claim a script-free result.
- Do not remove server-side validation when adopting native client constraints.
- State assumptions and compatibility evidence in the result. If targets are absent, flag the uncertainty before relying on a recently shipped feature.
- Summarize what changed, what JavaScript remains, why it remains, and how the result was verified.

## References

- Read [semantic-html.md](references/semantic-html.md) for document structure, native controls, accordions, navigation, forms, and media semantics.
- Read [modern-css.md](references/modern-css.md) for layout, selectors, responsive behavior, state, and animation.
- Read [native-capabilities.md](references/native-capabilities.md) for dialogs, popovers, forms, navigation, media, and browser APIs that may still need minimal orchestration.
- Read [safe-adoption.md](references/safe-adoption.md) for browser compatibility, accessibility, fallbacks, and review checks.
