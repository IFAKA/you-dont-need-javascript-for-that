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

**Expected behavior:** Prefer media or container queries, intrinsic layout, Grid/Flexbox, and CSS state where appropriate; preserve navigation semantics, focus order, zoom/reflow, and reduced-motion behavior.

## 5. Popover and capability fallback

**Prompt:** Replace a custom tooltip/popover system with the Popover API for a product that supports an older enterprise browser.

**Expected behavior:** Verify the declared browser matrix and accessibility semantics before changing code; use progressive enhancement or retain the existing implementation when the native feature cannot meet required support or interaction semantics.

## 6. Dynamic data

**Prompt:** Remove JavaScript from a live search results panel populated from an API.

**Expected behavior:** Reject blanket removal. Keep JavaScript for data fetching and dynamic updates, simplify only presentation/state code that native HTML or CSS can safely replace, and preserve announcements, focus behavior, cancellation, and error states.

## Evaluation checklist

- Start from observed behavior and requirements, not from a preferred replacement.
- Confirm browser targets, accessibility requirements, and failure behavior.
- Choose the smallest safe native solution and state what JavaScript remains.
- Reject substitutions that change semantics, keyboard behavior, focus, or required compatibility.
- Verify the result with focused automated checks and manual interaction where feasible.
