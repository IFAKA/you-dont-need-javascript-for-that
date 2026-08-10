# Token-Efficient Skill Architecture

## Goal

Maximize signal-to-noise without allowing a local JavaScript simplification to break behavior owned elsewhere in a large application.

## Design

Use a safety-first progressive-disclosure hybrid:

1. Keep `SKILL.md` as the mandatory control plane: audit, constraints, risk triage, impact-map gate, reference routing, smallest safe change, and verification.
2. Let local tasks satisfy the impact-map gate with a compact map and load only the domain reference they need.
3. Require connected tasks to load `references/integration-impact.md`, which expands the core gate across composition, rendering, DOM, bundles, events, replacement lifecycles, third parties, and project policy.
4. Keep domain detail in single-purpose references. Do not duplicate it in the core or load every reference by default.
5. Remain framework-agnostic. Real applications validate the generic risk model but do not contribute product-specific vocabulary or rules to the public skill.

## Evaluation

Behavioral scenarios must prove both paths: a self-contained disclosure should use little context, while a composed, dynamically updated interaction must trigger a deep cross-layer audit. Validation also checks package structure, reference links, and absence of project-specific coupling.

## Tradeoff

The impact-map gate adds a small fixed cost to every task. That cost is intentional: it is the minimum guardrail that makes conditional loading safe. Loading detailed integration guidance only on matching signals avoids paying the enterprise-audit token cost for local work.
