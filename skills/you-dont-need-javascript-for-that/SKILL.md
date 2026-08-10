---
name: you-dont-need-javascript-for-that
description: Audit frontend behavior and replace unnecessary JavaScript with accessible, maintainable native HTML and CSS while retaining minimal JavaScript when requirements demand it. Use for JavaScript-removal requests, native HTML/CSS rewrites, dependency-free UI simplification, or reviews of custom controls, dialogs, popovers, forms, navigation, responsive behavior, animation, browser APIs, and cross-layer frontend integrations.
---

# You Don't Need JavaScript for That

Prefer the web platform only when it preserves required behavior. Treat fewer moving parts as the goal, not zero JavaScript.

## Workflow

1. **Audit before editing.** Trace the current interaction, state, data flow, keyboard behavior, focus, announcements, validation, failure states, and tests. Record observable behavior that must remain.
2. **Establish constraints.** Find the project's declared browser targets, accessibility standard, design constraints, progressive-enhancement policy, and server-rendering requirements. Do not guess support from feature age.
3. **Triage risk.** Classify the change as **local** only when behavior, markup, styling, initialization, and consumers are contained in one understood component boundary, even if split across adjacent files. Classify it as **connected** when contracts cross that boundary through runtime composition, rendering layers, bundles, events, DOM replacement, third parties, or conflicting project policies. When uncertain, use connected.
4. **Pass the impact-map gate.** Before editing, list the changed behavior and every producer, consumer, lifecycle, and policy that can affect it. A local map may be one compact line. A connected map must use [integration-impact.md](references/integration-impact.md); stop or preserve the implementation when a required edge cannot be verified.
5. **Route references.** Read only the references whose conditions match the task. Never load all references by default.
6. **Choose the smallest safe change.** Preserve public behavior and remove only JavaScript made redundant by a native primitive. Prefer progressive enhancement over all-or-nothing rewrites.
7. **Keep necessary JavaScript.** Retain script for dynamic data, application state, cross-field or business validation, analytics, imperative browser APIs, and support gaps. Explain why each remaining piece belongs.
8. **Verify.** Run project-derived tests and inspect keyboard operation, focus order/restoration, accessible names and state, zoom/reflow, reduced motion, failure behavior, and required browsers.

## Decision Rules

- Reject a native replacement that weakens semantics, accessibility, security, required compatibility, or user-visible behavior.
- Do not recreate a native control with generic elements and ARIA. Use native semantics first; use ARIA only to fill a real semantic gap.
- Do not move business logic into CSS or markup merely to claim a script-free result.
- Do not remove server-side validation when adopting native client constraints.
- State assumptions and compatibility evidence in the result. If targets are absent, flag the uncertainty before relying on a recently shipped feature.
- Summarize what changed, what JavaScript remains, why it remains, and how the result was verified.

## References

| Read | Only when |
| --- | --- |
| [semantic-html.md](references/semantic-html.md) | Changing structure, controls, forms, navigation, disclosure, or media semantics |
| [modern-css.md](references/modern-css.md) | Replacing script-driven layout, responsiveness, selectors, state styling, or animation |
| [native-capabilities.md](references/native-capabilities.md) | Considering dialogs, popovers, validation, URL state, media, or another browser API |
| [safe-adoption.md](references/safe-adoption.md) | Support, accessibility behavior, fallback, or failure-mode evidence needs detailed review |
| [integration-impact.md](references/integration-impact.md) | Risk triage is connected or uncertain; this expands the mandatory impact-map gate |
