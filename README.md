# You Don’t Need JavaScript for That

A Codex skill for auditing frontend behavior and replacing unnecessary JavaScript with accessible, maintainable web-platform features. It favors the smallest safe native solution—not JavaScript removal at any cost.

The skill covers semantic HTML, native controls, modern CSS, dialogs, popovers, forms, navigation, media, compatibility, accessibility, fallbacks, and review.

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
2. Check browser targets and accessibility requirements.
3. Select the smallest safe native HTML/CSS solution.
4. Keep minimal JavaScript for dynamic data, application state, cross-field rules, imperative APIs, or compatibility gaps.
5. Verify behavior, accessibility, fallbacks, and required browsers.

## Examples

- Replace a custom accordion with `details` and `summary` when their behavior fits.
- Replace JavaScript layout calculations with Grid, Flexbox, intrinsic sizing, or container queries.
- Use native form constraints for field-local validation while keeping server and cross-field validation.
- Adopt `dialog` or the Popover API with minimal orchestration and a compatible fallback.
- Reject a native rewrite when it would harm accessibility or required browser support.

See [EVALUATION.md](EVALUATION.md) for behavioral evaluation scenarios.

## License

[MIT](LICENSE)
