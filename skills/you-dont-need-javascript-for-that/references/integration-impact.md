# Integration Impact Mapping

Use this reference after the core workflow classifies a change as connected or uncertain. It expands the mandatory impact-map gate; it does not replace or relax it.

## Build the map

Record evidence, not assumptions, for every matching boundary:

| Boundary | Trace | Failure to prevent |
| --- | --- | --- |
| Runtime composition | Inheritance, overrides, extension points, precedence, conditional implementations | Editing a file that is not active or bypassing downstream overrides |
| Rendering contract | Server/controller data, template conditions, generated attributes, IDs, classes, and element order | Breaking the DOM shape or state expected by another layer |
| Module contract | Imports, exports, bundle entry points, side effects, load order, plugin registration, and initialization | Removing code that activates or configures behavior elsewhere |
| Event contract | Direct and delegated listeners, custom events, event names, payloads, targets, propagation, and cancellation | Silencing consumers or changing timing and ownership |
| DOM lifecycle | Initial render, asynchronous or fragment replacement, insertion, teardown, reinitialization, and duplicate-binding protection | Working only on first load or leaking stale handlers and state |
| External observers | Analytics, experimentation, consent, monitoring, embedded content, and other third-party hooks | Losing required signals or changing compliance behavior |
| Project policy | Declared browser targets, actual usage evidence, accessibility requirements, rendering modes, and test gates | Adopting a feature that violates the effective support contract |

For each edge, capture **producer → contract → consumer**, where it is initialized, and how to verify it. Search by stable contract markers—selectors, attributes, event names, exports, template variables, and initialization calls—rather than by filenames alone.

## Resolve policy conflicts

When configuration, documentation, tests, and existing code disagree:

1. Treat the strictest plausible requirement as active until evidence resolves the conflict.
2. Prefer explicit maintained policy over inference from isolated syntax.
3. Report the contradiction and its effect on the proposed native feature.
4. Keep a fallback or the existing behavior when required support remains uncertain.

## Set verification gates

Derive checks from the map instead of applying a generic test list:

- exercise every render and composition path that can select the changed behavior;
- verify initial load and each partial-update or reinitialization path;
- assert DOM contracts and public events at consumer boundaries;
- confirm bundle, plugin, and third-party hooks still initialize exactly as required;
- run the repository's focused tests, build checks, and required browser/accessibility checks;
- compare analytics or monitoring signals when they are part of the contract.

## Stop conditions

Do not remove the JavaScript when an active implementation cannot be identified, a consumer cannot be traced, lifecycle behavior is untested, browser policy is unresolved, or the replacement changes a required public contract. Narrow the change, add evidence, or retain minimal orchestration instead.
