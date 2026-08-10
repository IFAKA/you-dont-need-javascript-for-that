# You Don’t Need JavaScript for That

A Codex skill for auditing frontend behavior and replacing unnecessary JavaScript with accessible, maintainable web-platform features. It favors the smallest safe native solution—not JavaScript removal at any cost.

The skill uses a lean mandatory safety workflow and loads detailed references only when the task needs them. It covers semantic HTML, modern CSS, browser capabilities, compatibility, accessibility, fallbacks, and cross-layer integration impact without assuming a framework.

## Install

### Ask Codex

Ask Codex to install the skill from its GitHub path:

```text
Use $skill-installer to install https://github.com/IFAKA/you-dont-need-javascript-for-that/tree/main/skills/you-dont-need-javascript-for-that
```

Restart Codex or begin a new session after installation so the skill is discovered.

### Manual installation

Clone the repository, then copy the packaged skill into your personal Codex skills directory:

```sh
git clone https://github.com/IFAKA/you-dont-need-javascript-for-that.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R you-dont-need-javascript-for-that/skills/you-dont-need-javascript-for-that \
  "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Start a new Codex session and invoke it explicitly:

```text
Use $you-dont-need-javascript-for-that to simplify this custom accordion without changing its behavior.
```

No installer script, package manager, build step, or runtime dependency is required.

## What it does

The skill instructs Codex to:

1. Audit existing behavior before editing.
2. Check browser targets, accessibility requirements, and current standards evidence.
3. Triage local versus connected risk and map affected contracts before editing.
4. Load only the references that match the detected risk and feature.
5. Select the smallest safe native HTML/CSS solution.
6. Keep minimal JavaScript for dynamic data, application state, cross-field rules, imperative APIs, or compatibility gaps.
7. Verify behavior, accessibility, fallbacks, integrations, and required browsers.

For feature freshness, the skill checks live standards and compatibility sources at task time; it does not depend on a bundled snapshot or an additional runtime skill.

## Examples

- Replace a custom accordion with `details` and `summary` when their behavior fits.
- Replace JavaScript layout calculations with Grid, Flexbox, intrinsic sizing, or container queries.
- Use native form constraints for field-local validation while keeping server and cross-field validation.
- Adopt `dialog` or the Popover API with minimal orchestration and a compatible fallback.
- Reject a native rewrite when it would harm accessibility or required browser support.

See [EVALUATION.md](EVALUATION.md) for behavioral evaluation scenarios.

## License

[MIT](LICENSE)
