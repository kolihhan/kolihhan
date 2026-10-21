# Repo Understanding

Use for unfamiliar, old, inherited, recovered, or poorly documented repositories where the goal is to reconstruct what the code actually does.

## Preferred existing skills

Verify availability at runtime. Preferred candidates:

- `egonex-ai/understand-anything:understand` — broad codebase structure, component relationships, knowledge graph when useful.
- `backnotprop/pstack:how` — subsystem ownership, layering, runtime flow, and placement questions.
- relevant `obra/superpowers:*` skills — process discipline, debugging/review/verification, and transition into implementation when changes are requested.

Add a persistent codebase map only when the user needs reusable onboarding/documentation. Do not generate documentation just to feel productive.

## Skill discovery keywords

Search current skills for:

- codebase understanding
- repository mapping
- architecture / dependency analysis
- execution-flow tracing
- knowledge graph
- code documentation / onboarding

Prefer `egonex-ai/understand-anything:understand` when available for full-repo understanding, then targeted tools for unresolved flows.

## Workflow

1. Read repo-local instructions and existing docs, but do not treat README claims as proof of implementation.
2. Identify entry points, major modules, configuration, tests, persistence, external services, and build/runtime boundaries.
3. Trace representative real flows through source code: request -> logic -> storage/tool/API -> response/output.
4. Inspect recent/relevant history when it changes the interpretation.
5. Cross-check documentation against code and tests.
6. Build the smallest useful mental model: architecture, important files, data/control flow, invariants, failure points.
7. Distinguish what is proven from code from what is inferred.
8. If implementation work follows, hand off to Development with the discovered constraints intact.

## Grill handoff

When the user asks to challenge the reconstructed understanding, compose with `grill-mode.md`; use adversarial review to attack assumptions, not to replace source tracing.

## Evidence rules

For important claims, point to concrete evidence such as file paths, symbols, tests, configuration, commits, or observed runtime behavior.

Use:

- **FACT** — directly visible in code/config/tests/runtime.
- **INFERENCE** — likely interpretation from multiple facts.
- **UNKNOWN** — cannot be established from available evidence.

Do not invent original product intent, production scale, historical ownership, user counts, deployment details, or business impact that the repository does not establish.

## Avoid

- reading only README and summarizing it;
- scanning filenames without tracing behavior;
- refactoring while the task is only to understand;
- modernizing dependencies in historical projects;
- treating generated/dependency code as core evidence when source code exists.
