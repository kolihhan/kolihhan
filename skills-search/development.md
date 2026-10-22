# Development

Default engineering workflow for feature work, bug fixes, refactors, production changes, and project development.

Follow the root `AGENTS.md` for precedence, scope/irreversible actions, reporting evidence, and compression safety. This file adds development-specific routing and execution guidance only.

## Preferred existing skills

Verify availability at runtime.

### Main development OS

Use relevant `obra/superpowers:*` skills, especially:

- `obra/superpowers:brainstorming`
- `obra/superpowers:writing-plans`
- `obra/superpowers:test-driven-development`
- `obra/superpowers:systematic-debugging`
- `obra/superpowers:requesting-code-review`
- `obra/superpowers:verification-before-completion`

Repository/user instructions outrank a skill's default ceremony. Use the smallest process that still preserves correctness and verification.

### Selected PStack toolbox

Use only when the task benefits from it:

- `backnotprop/pstack:how` — unfamiliar subsystem, ownership/layering, runtime flow.
- `backnotprop/pstack:architect` — non-trivial interfaces/module shape before coding.
- `backnotprop/pstack:arena` — multiple genuinely plausible approaches where one-shot choice is risky.
- `backnotprop/pstack:blast-radius` — inspect what a change could break beyond the diff.
- `backnotprop/pstack:interrogate` — adversarial or multi-angle review for important changes.

Do not run PStack FULL by default. Avoid ceremony that does not reduce risk.

### Optional scope / overengineering guard

- `lennney/stop-that-shit:stop-that-shit` — use when task boundaries are unusually strict, review/answer must remain read-only, implementation is drifting into speculative hardening or unrelated scope, or verification/delegation is repeating without new evidence.

Treat it as a guardrail, not a separate workflow mode. Ordinary validation, retries, dependencies, or normal verification are not enough to trigger it. Prefer the host Guard when runtime enforcement of file, mutation, dependency, or subagent boundaries is specifically useful; otherwise the Skill alone is sufficient.

### Communication/token layer

- `juliusbrussee/caveman:caveman` when available and concise output is useful.
- `lennney/stop-that-shit:stss` for reader-facing prose when defensive disclaimers, stacked hedging, or self-protective narration need tightening without deleting meaningful uncertainty or limitations.

Use Caveman for progress updates, routine explanation, and context preservation subject to the root `AGENTS.md` compression rule. Use STSS only for writing/auditing prose; do not treat it as a general code or workflow skill.

## Skill discovery keywords

Before implementation, verify the currently available skills for:

- brainstorming / design
- TDD
- systematic debugging
- implementation-plan execution
- code review
- blast radius / adversarial review
- scope control / overengineering guard
- verification before completion
- concise communication / defensive-writing cleanup

## Workflow

1. Read target repo instructions, current state, tests, and relevant implementation.
2. Classify the change by risk/scope; use the smallest sufficient design process.
3. For unfamiliar code, invoke Repo Understanding first rather than guessing architecture.
4. Define observable success/failure before implementation.
5. Write or identify the test/check that exposes the current gap.
6. Implement the smallest useful change; avoid unrelated modernization/refactors.
7. Run focused tests, then the broader relevant suite when warranted/available.
8. Review the diff for accidental scope, regressions, secrets, and operational risk.
9. Use `backnotprop/pstack:blast-radius` / `backnotprop/pstack:interrogate` only when risk justifies it.
10. Use `obra/superpowers:verification-before-completion` before saying done when available.

## Grill handoff

When the user asks to grill/challenge/red-team the implementation, compose this mode with `grill-mode.md` instead of inventing another review process.

`openai/openai-agents-python:.agents/skills/implementation-final-review` is a strong zero-base final implementation audit candidate, but its own trigger contract is restrictive: use it only when explicitly invoked by the user or when repository instructions authorize automatic invocation.

## Development-specific guardrails

- Do not silently weaken tests to make implementation pass.
- Preserve public interfaces unless the requested change requires otherwise.
- Stop broad/risky changes when the evidence does not justify them.
- Prefer one working path over extra abstractions.
