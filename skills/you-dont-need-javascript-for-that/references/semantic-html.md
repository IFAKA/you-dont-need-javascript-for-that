# Semantic HTML and Native Controls

## Start from meaning

- Preserve the document outline, landmarks, source order, labels, descriptions, and relationships before changing interaction code.
- Prefer elements with built-in semantics and keyboard behavior: `button`, links with `href`, form controls, `details`/`summary`, `dialog`, and media elements.
- Use a link for navigation and a button for an action. Do not make a `div` interactive to avoid native styling.
- Keep DOM/source order aligned with reading and focus order. Do not use CSS reordering to disguise incorrect structure.

## Common candidates

### Disclosure and accordion

Use `details` and `summary` when each item is an independent disclosure and their native behavior matches the requirements. Confirm whether multiple panels may remain open, how initial state is represented, and whether styling and find-in-page behavior are acceptable. Keep minimal JavaScript when coordinated single-open behavior or application state must be synchronized and cannot be expressed safely by supported native behavior.

### Navigation

Use `nav`, lists when the grouping is meaningful, and real links. CSS can own visual breakpoints, but a menu still needs an operable control, an exposed state, focus management where appropriate, and a usable expanded layout when scripts fail. Do not substitute hover-only menus for an interaction available to keyboard and touch users.

### Forms

- Associate every control with a persistent label; placeholders are not labels.
- Use suitable types and attributes such as `email`, `url`, `number`, `date`, `required`, `min`, `max`, `minlength`, `maxlength`, `pattern`, and `autocomplete` when they match the data contract.
- Prefer `fieldset` and `legend` for related choices.
- Keep server-side validation authoritative. Use JavaScript for cross-field, asynchronous, or business-specific rules and expose errors programmatically and visibly.
- Do not disable submission merely because a CSS validity selector can style a field.

### Media

Use `picture`, `source`, `srcset`, `sizes`, native lazy loading, `video`, `audio`, captions, and transcripts where they satisfy the content need. Preserve controls and alternatives; do not replace a usable native player solely to remove its default appearance.

## Native does not mean sufficient

Verify accessible names, descriptions, state announcements, keyboard behavior, focus visibility, target size, contrast, error recovery, and high-contrast modes. Native semantics provide a foundation, not a waiver from testing.
