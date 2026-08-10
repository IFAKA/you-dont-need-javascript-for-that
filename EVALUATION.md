# Behavioral Evaluation Scenarios

Use these scenarios to evaluate whether the skill favors the web platform without treating JavaScript removal as an absolute goal.

## 1. Custom accordion

**Prompt:** Replace a click-handler-based FAQ accordion with native HTML while preserving keyboard and screen-reader behavior.

**Expected behavior:** Audit the current single/multiple-open behavior and browser targets, prefer `details`/`summary` when its semantics fit, preserve visible focus and heading structure, and retain JavaScript if requirements exceed interoperable native behavior.

## 2. Modal dialog

**Prompt:** Remove the JavaScript modal implementation from an account settings flow.

**Expected behavior:** Check focus restoration, dismissal, initial focus, form submission, and browser requirements; use `dialog` with `showModal()` and minimal orchestration JavaScript rather than claiming a fully script-free modal when opening it still requires behavior.

## 3. Form validation

**Prompt:** Rewrite a registration form to use native validation instead of a validation library.

**Expected behavior:** Use semantic input types, constraints, labels, and accessible error messaging for field-local rules; retain minimal JavaScript for password confirmation or other cross-field/business rules; never remove server-side validation.

## 4. Responsive navigation and layout

**Prompt:** Remove viewport-resize listeners and JavaScript layout calculations from a responsive page.

**Expected behavior:** Classify the understood component boundary, load `modern-css.md` for the layout and responsive rewrite, and load `semantic-html.md` when navigation structure or controls change. Prefer media or container queries, intrinsic layout, Grid/Flexbox, and CSS state where appropriate; preserve navigation semantics, focus order, zoom/reflow, and reduced-motion behavior. Do not load unrelated capability or integration guidance without another matching signal.

## 5. Popover and capability fallback

**Prompt:** Replace a custom tooltip/popover system with the Popover API for a product that supports an older enterprise browser.

**Expected behavior:** Load `native-capabilities.md` for the proposed Popover API and `safe-adoption.md` for compatibility, accessibility, and fallback evidence. Verify the declared browser matrix and interaction semantics before changing code; use progressive enhancement or retain the existing implementation when the native feature cannot meet required support or behavior.

## 6. Dynamic data

**Prompt:** Remove JavaScript from a live search results panel populated from an API.

**Expected behavior:** Reject blanket removal. Keep JavaScript for data fetching and dynamic updates, simplify only presentation/state code that native HTML or CSS can safely replace, and preserve announcements, focus behavior, cancellation, and error states.

## 7. Local disclosure with a low context budget

**Prompt:** Simplify a self-contained disclosure component whose markup, styles, and click handler live together and have no external consumers.

**Expected behavior:** Confirm the behavior and constraints, classify the change as local, write a compact one-boundary impact map, and load only the semantic HTML reference. Do not read integration, CSS, or browser-capability guidance without a matching signal. Prefer `details`/`summary` only when their behavior fits.

## 8. Cross-layer interaction in a composed application

**Prompt:** Replace a custom panel controller in an application where server output selects templates, modules may be overridden at runtime, bundles register delegated events, page fragments can be replaced without a full navigation, and analytics observe the same interactions.

**Expected behavior:** Classify the change as connected before editing and load the integration-impact reference. Map runtime composition, server/template/DOM contracts, bundle and plugin initialization, delegated/custom events, replacement lifecycle, third-party hooks, and the project-derived browser policy. Retain JavaScript or stop the rewrite when evidence is incomplete or the native replacement would break a consumer.

## 9. Ambiguous consumers and support policy

**Prompt:** Remove a shared interaction helper, but some event consumers cannot be located and the documented browser policy conflicts with project configuration.

**Expected behavior:** Classify the change as uncertain rather than local, load `integration-impact.md`, and map the known contracts and policy conflict. Stop the rewrite or retain the existing JavaScript until the missing consumers and effective browser requirements are resolved; do not use absent evidence as permission to simplify.

## Evaluation checklist

- Start from observed behavior and requirements, not from a preferred replacement.
- Confirm browser targets, accessibility requirements, and failure behavior.
- Triage local versus connected risk and complete an impact map before editing.
- Load only references whose routing conditions match; connected changes must load integration guidance.
- Choose the smallest safe native solution and state what JavaScript remains.
- Reject substitutions that change semantics, keyboard behavior, focus, or required compatibility.
- Verify the result with focused automated checks and manual interaction where feasible.
