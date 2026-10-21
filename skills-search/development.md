# Development

Default engineering workflow for feature work, bug fixes, refactors, production changes, and project development.

## Default stack

`Superpowers = main development OS`

Use its disciplined flow for requirements/design, planning when warranted, TDD, debugging, review, and verification.

`Selected PStack = specialist toolbox`

Use only when the task benefits from it:

- `how` — unfamiliar subsystem, ownership/layering, runtime flow.
- `architect` — non-trivial interfaces/module shape before coding.
- `arena` — multiple genuinely plausible approaches where one-shot choice is risky.
- `blast-radius` — inspect what a change could break beyond the diff.
- `interrogate` — adversarial or multi-angle review for important changes.

Do not run PStack FULL by default. Avoid ceremony that does not reduce risk.

`Caveman = communication/token layer`

Use it to keep progress and explanations compact. It does not replace engineering rigor.

## Skill discovery keywords

Before implementation, verify the currently available skills for:

- brainstorming / design
- TDD
- systematic debugging
- implementation-plan execution
- code review
- blast radius / adversarial review
- verification before completion
- concise communication

## Workflow

1. Read target repo instructions, current state, tests, and relevant implementation.
2. Classify the change by risk/scope; use the smallest sufficient design process.
3. For unfamiliar code, invoke Repo Understanding first rather than guessing architecture.
4. Define observable success/failure before implementation.
5. Write or identify the test/check that exposes the current gap.
6. Implement the smallest useful change; avoid unrelated modernization/refactors.
7. Run focused tests, then the broader relevant suite.
8. Review the diff for accidental scope, regressions, secrets, and operational risk.
9. Use `blast-radius` / `interrogate` only when risk justifies it.
10. Verify the final behavior with real evidence before saying done.

## Guardrails

- No speculative refactor while fixing a bounded issue.
- No "tests should pass" claims without running them when execution is available.
- Do not silently weaken tests to make implementation pass.
- Preserve public interfaces unless the requested change requires otherwise.
- Stop broad/risky changes when the evidence does not justify them.
- Prefer one working path over extra abstractions.

## Completion evidence

A completion report should name what changed and the evidence used to verify it: test results, build output, live behavior, diff review, or another task-appropriate check.
