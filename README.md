# You Don’t Need JavaScript for That

> A standards-first Codex skill for replacing unnecessary JavaScript with accessible, maintainable web-platform features.

[![Install with Codex](https://img.shields.io/badge/Codex-install%20skill-111827?style=flat-square)](https://github.com/IFAKA/you-dont-need-javascript-for-that/tree/main/skills/you-dont-need-javascript-for-that)
[![License: MIT](https://img.shields.io/badge/license-MIT-16a34a?style=flat-square)](LICENSE)

## The idea

The goal is not to remove JavaScript at any cost. The goal is to keep the smallest safe implementation that preserves behavior, accessibility, compatibility, and integration contracts.

This skill helps Codex evaluate whether HTML, CSS, browser APIs, or native form behavior can own a task—and retain JavaScript for application state, dynamic data, business logic, analytics, imperative APIs, and unsupported browser capabilities.

## Use it when

- a component measures or positions itself in JavaScript even though CSS can express the constraint;
- a custom accordion, dialog, menu, form, or validation flow may have a native equivalent;
- JavaScript is carrying state or structure that HTML already understands;
- you want a semantic and accessibility audit before simplifying a component;
- you need to reduce markup and styles without weakening the design.

## Install

### Ask Codex

```text
Use $skill-installer to install https://github.com/IFAKA/you-dont-need-javascript-for-that/tree/main/skills/you-dont-need-javascript-for-that
```

Restart Codex or begin a new session after installation so the skill is discovered.

### Manual installation

```sh
git clone https://github.com/IFAKA/you-dont-need-javascript-for-that.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R you-dont-need-javascript-for-that/skills/you-dont-need-javascript-for-that \
  "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Then invoke it explicitly:

```text
Use $you-dont-need-javascript-for-that to audit this custom accordion and preserve its visual design.
```

No package manager, build step, or runtime dependency is required.

## What the skill does

1. Audits the markup and class-driven structure before editing.
2. Separates semantics from presentation, layout, branding, and interaction styling.
3. Replaces fake controls and structural workarounds only when native HTML expresses the same meaning and behavior.
4. Removes JavaScript made redundant by the markup change.
5. Verifies accessibility, focus, responsive behavior, and the restored visual design.
6. Explains which JavaScript remains—and why it still belongs in JavaScript.

## Examples

| Instead of | Prefer when it fits |
| --- | --- |
| JavaScript layout measurements | normal flow, Grid, Flexbox, intrinsic sizing, or container queries |
| custom field-local validation | native input types and constraint attributes |
| a custom disclosure controller | `details` and `summary` |
| a fully custom modal foundation | `dialog` with minimal orchestration |
| script-selected responsive images | `picture`, `srcset`, and `sizes` |

These are decision points, not blind rewrites. Keep JavaScript for remote data, application state, cross-field rules, imperative APIs, analytics, and compatibility gaps.

## Part of a pair

If the remaining problem is generic markup or CSS compensating for missing semantics, use [You Don’t Need CSS for That](https://github.com/IFAKA/you-dont-need-css-for-that). Together, the pair helps keep frontend implementations close to the platform without treating simplicity as a dogma.

## Repository map

- [`skills/you-dont-need-javascript-for-that/`](skills/you-dont-need-javascript-for-that/) — installable skill package.
- [`skills/you-dont-need-javascript-for-that/references/`](skills/you-dont-need-javascript-for-that/references/) — focused guidance loaded when needed.
- [`EVALUATION.md`](EVALUATION.md) — behavioral evaluation rubric and examples.
- [`docs/`](docs/) — maintainer and learning notes.

## License

[MIT](LICENSE)
