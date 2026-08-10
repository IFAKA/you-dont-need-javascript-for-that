# Modern CSS

## Layout

- Prefer normal flow, Flexbox, Grid, intrinsic sizing, `min()`, `max()`, `clamp()`, and logical properties over JavaScript measurement and positioning.
- Use `aspect-ratio` and `object-fit` for stable media geometry.
- Avoid layout reads followed by writes in script when CSS can express the constraint directly.

## Responsive behavior

- Prefer media queries for viewport or user preferences and container queries for component-local adaptation.
- Use responsive images rather than selecting image sources with viewport JavaScript.
- Test zoom, text enlargement, narrow reflow, long content, localization, and input modalities; matching a screenshot at a few widths is insufficient.
- Keep content and actions available at every breakpoint. CSS hiding is not a replacement for a coherent interaction model.

## Selectors and state

- Use structural and relational selectors such as `:checked`, `:target`, `:focus-visible`, `:focus-within`, and `:has()` only when the represented state belongs in the document and required browsers support them.
- Do not encode durable application state, authorization, data fetching, or business rules in CSS.
- Avoid checkbox hacks when a native disclosure, dialog, popover, or small explicit controller communicates state more accurately.

## Animation

- Prefer CSS transitions and keyframes for presentational motion.
- Respect `prefers-reduced-motion`; remove nonessential motion and ensure essential state changes remain understandable without animation.
- Use JavaScript when animation depends on runtime data, coordinated application state, or an imperative API, but let CSS own styling where practical.
- Avoid animating layout-heavy properties when transforms or opacity preserve the intended result.

## Review

Confirm focus indicators, forced-colors behavior, content visibility, print behavior when relevant, and absence of hover-only information. Verify that selectors fail safely rather than leaving controls inaccessible.
