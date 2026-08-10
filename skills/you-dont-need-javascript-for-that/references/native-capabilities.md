# Native Browser Capabilities

## Dialogs

Use `dialog` for modal or non-modal dialogs when required browsers support the needed behavior. Opening a modal normally still needs a small call to `showModal()`; closing may use a form with `method="dialog"` or minimal script. Verify initial focus, focus containment, Escape behavior, focus restoration, nested interactions, backdrop, and submitted values. Do not treat a dialog as ordinary page navigation.

## Popovers

Consider the Popover API for top-layer, light-dismissable UI and declarative invokers where semantics and support fit. A popover is not automatically a tooltip, menu, listbox, or dialog: choose the correct interaction semantics and keyboard model separately. Retain a fallback or existing implementation when required browsers lack the necessary behavior.

## Forms and validation

Use native constraint validation for field-local syntactic constraints that match the data model. Keep JavaScript for cross-field comparisons, conditional rules, async uniqueness checks, formatted widgets, and application-specific error summaries. Keep validation on the server regardless of client behavior.

## Navigation and URL state

Prefer links, forms, anchors, fragment navigation, and server responses when they provide the required experience. Keep client-side routing or JavaScript state when the product genuinely requires partial updates, optimistic behavior, dynamic history management, or unsaved-state coordination. Preserve deep links and meaningful URLs.

## Media and loading

Prefer responsive image markup, native lazy loading, preload hints used sparingly, media controls, captions, and declarative source selection. Keep JavaScript for adaptive streaming, custom synchronized experiences, analytics required by the product, or runtime media orchestration.

## Other browser features

Evaluate declarative or native facilities such as `inert`, `hidden`, `<template>`, Web Components, scroll snap, anchor positioning, and view transitions against the actual target matrix. Some are primitives rather than no-code replacements and may require JavaScript to instantiate or coordinate them.

## Boundary test

Ask whether the behavior is presentation, document semantics, user preference, application state, remote data, or business logic. HTML and CSS should usually own the first three; JavaScript often remains appropriate for the latter three.
