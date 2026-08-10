# Safe Adoption and Review

## Compatibility

1. Locate declared targets in project configuration, support policy, analytics, or documentation.
2. Verify each proposed feature against current authoritative sources at task time. Use the source that owns each claim:
   - HTML elements, DOM behavior, and browser APIs: [WHATWG HTML Living Standard](https://html.spec.whatwg.org/)
   - CSS syntax and behavior: [CSS Working Group specifications and drafts](https://drafts.csswg.org/)
   - ECMAScript language behavior: [TC39 ECMA-262](https://tc39.es/ecma262/)
   - Browser and runtime support: [MDN Browser Compatibility Data](https://github.com/mdn/browser-compat-data)
   - Accessibility interaction patterns: [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/) and the applicable WCAG guidance
3. Compare that evidence with the project's declared target matrix and the exact behavior required, including mobile and embedded browsers. Record the feature, source URL, checked date, target browsers, and any caveat.
4. Check whether partial support, missing accessibility mappings, or styling differences affect the use case.
5. Prefer progressive enhancement when the baseline remains complete and operable.
6. Keep a fallback or the existing JavaScript when the unsupported path would block a required task.

Do not add a polyfill whose weight and maintenance exceed the JavaScript being removed without documenting that tradeoff.

## Accessibility

Test with keyboard alone and, when feasible, representative screen reader/browser combinations. Verify:

- semantic role, accessible name, description, value, and state;
- logical reading and focus order, visible focus, initial focus, and restoration;
- activation, dismissal, Escape behavior, and no keyboard traps;
- errors that are identified, associated, announced, and recoverable;
- zoom, reflow, text spacing, contrast, forced colors, touch targets, and reduced motion;
- usable content when CSS, JavaScript, a request, or an enhancement fails.

ARIA does not repair the wrong interaction model. Prefer the correct native element; add ARIA only when it accurately exposes missing semantics.

## Fallback strategy

- **Baseline first:** deliver the core task with broadly supported HTML.
- **Enhanced presentation:** layer CSS features behind natural fallback behavior or `@supports` where needed.
- **Enhanced interaction:** add minimal JavaScript or a newer API only when detection succeeds.
- **Failure path:** ensure unsupported features do not hide content, strand focus, or block submission/navigation.

## Review checklist

- Compare behavior before and after, including edge and failure states.
- Inspect the DOM and accessibility tree, not only pixels.
- Test required browsers and input modes.
- Confirm server-side security and validation remain intact.
- Remove obsolete listeners, dependencies, state, styles, and tests only after the replacement is verified.
- Add or update behavior-focused tests rather than asserting implementation trivia.
- Document compatibility evidence, fallback, retained JavaScript, and known limitations.
