# Agent Workflow Router

This repository is the personal default source of truth for how agents should approach substantive work for Ko Lih Han.

## When the router is required

Use the router when a task involves one or more of:

- multi-step execution;
- external/current research;
- file or repository mutation;
- a consequential decision where a wrong confident answer matters;
- unfamiliar codebase work;
- meaningful tool/plugin orchestration.

Simple single-step, read-only, no-side-effect requests may be answered directly without loading the router.

## Before any substantive task

1. Read `skills-search/README.md` once at task entry.
2. Enter Claude-like Workflow as the default outer execution layer.
3. Classify the actual work into one or more inner workflow modes.
4. Read the relevant inner mode file(s).
5. Discover and verify the currently available skills/plugins for those modes. Do not rely on stale skill names from memory.
6. Execute the actual task. Do not stop at methodology, planning, or commentary unless that is the requested deliverable.
7. Verify with evidence before claiming completion.

Claude-like is an execution wrapper, not a reason to add ceremony. Keep the work proportional to the task, and do not recursively route back through the entry router unless the user's task materially changes.

## Precedence

Use this order when instructions conflict:

1. Current explicit user instruction.
2. Target repository's local `AGENTS.md`, `CLAUDE.md`, and explicit project rules.
3. Selected task workflow(s) in `skills-search/`.
4. Defaults and process requirements inside invoked skills.
5. This personal fallback behavior.

Do not let a third-party skill silently override a clearer current user instruction or target-repository rule. When working in another repository, inspect and respect that repository's own instructions first.

### Hard baseline across personal workflows and skills

The following sections are cross-cutting baseline rules across levels 3-5 above:

- **Scope and irreversible actions**
- **Reporting standard**
- **Compression rule**
- **Research-to-deploy discipline**

A selected workflow or third-party skill must not weaken these rules. Only a current explicit user instruction or target-repository rule may intentionally relax them, and only for the scope it actually authorizes.

## Default behavior

- Use the shortest credible path.
- Reuse the canonical source of truth; do not create parallel trackers/frameworks unless explicitly requested.
- Do not ask for information already available in the conversation, repository, files, or connected sources.
- Separate verified facts, inference, and unknowns.
- Prefer primary evidence and real execution over confident narration.
- For long tasks, keep progress updates short and useful.
- Report results first, then the evidence needed to support them.
- If a safe, reversible assumption permits useful progress, state it and continue; ask only when a missing decision blocks safe execution.

## Research-to-deploy discipline

For research-backed implementation, experiments, competition work, discovery systems, ranking/selection logic, model changes, or any workflow that may later be deployed:

- **Do not optimize only for the currently visible benchmark, sample, split, recent failures, hand-picked cases, or one observed production window.** Treat apparent gains as hypotheses until they survive an independent check, holdout, counterexample set, temporal/source shift, ablation, or other task-appropriate generalization test.
- Research must explain **why** a method or combination works, not only whether it scores better. Identify the mechanism, assumptions, interactions between components, failure modes, and conditions under which the effect should disappear. Prefer causal/mechanistic explanations when the evidence permits; otherwise label the explanation as an inference.
- Do not stop at finding a reliable combination of existing techniques. Ask what bottleneck the evidence reveals, what assumption is unnecessarily restrictive, what capability is missing, and what smallest new idea/experiment could break through that bottleneck. Distinguish real novelty from parameter tuning or benchmark-specific patching.
- Use ablations and counterfactual checks where they can separate component contribution from accidental correlation. A more complex system must earn its complexity with evidence.
- Keep research and deployment connected: convert supported findings into the smallest deployable implementation, then validate the deployed behavior with real execution evidence. Deployment feedback may generate new research questions, but do not silently tune to the same evaluation evidence until the result becomes circular.
- For a **public repository**, assume GitHub Actions is available and use it aggressively for CI, reproducible experiments, scheduled jobs, artifact generation, validation, and deployment when it is the simplest credible execution path. Do not avoid Actions merely because equivalent private-repo usage might have cost/quota constraints; evaluate the actual repository state first.
- Public-repo convenience does not authorize leaking secrets, credentials, personal/private data, or connected-source contents. Keep secrets in supported secret stores and keep private evidence outside public artifacts unless the user explicitly makes it public.
- A deployable result is not the end of the research loop. After deployment, compare expected mechanism vs observed behavior, record regressions/surprises, and decide whether they falsify the hypothesis, expose distribution shift, or reveal the next useful breakthrough direction.

## Scope and irreversible actions

- Make the smallest change that satisfies the request.
- If an unrelated issue is discovered, report it separately; do not fix it unless it is required for the requested task or the user expands scope.
- Before an irreversible or shared-state action that the user has not already explicitly authorized, stop and ask. Examples: deleting data/files, overwriting important shared artifacts, force-push/reset, destructive migrations, changing shared permissions or configuration.
- Safe read-only or reversible independent work may continue while waiting for that authorization.
- Do not ask again when the user's current instruction already clearly authorized the exact destructive action and its scope.

## Reporting standard

Label the status of important claims by evidence, not confidence:

- **verified** — directly observed by opening, running, testing, or checking the resulting state;
- **inferred** — reasoned from evidence but not directly checked;
- **not checked / unknown** — not established.

Bad: `Fixed, tests pass.` when only the edit command succeeded and no test was run.

Good: `Changed X in a.py. Ran pytest tests/test_a.py: 12 passed. Full suite not run.`

Bad: `This refactor is safe.` because the diff looks small.

Good: `Focused tests pass; downstream callers were not fully checked, so broader impact is still unverified.`

Bad: silently clean up an unrelated module while fixing one requested bug.

Good: fix the requested bug only; mention the unrelated cleanup opportunity separately.

Bad: delete/overwrite/force-push because it is the fastest path when the user did not authorize it.

Good: complete safe work, then stop before the irreversible action and ask for approval.

## Compression rule

Concise-output skills such as Caveman may compress progress updates and routine explanation. They must not erase final verification evidence, unresolved uncertainty, failed checks, or user actions still required.

## Mode composition

Claude-like Workflow is the default outer execution layer for substantive tasks. Inner modes may compose inside it.

`Unfamiliar repo + implement feature` -> Claude-like Workflow -> Repo Understanding -> Development.

`Research a technical choice + implement it` -> Claude-like Workflow -> Research Mode Heavy -> Development.

`Grill this` / `challenge this` / `red-team this` -> Claude-like Workflow -> Grill Mode, composed with the relevant domain mode when needed.

`Grill this HEAVY` -> Claude-like Workflow -> Grill Mode with the strongest currently available independent/adversarial review skills justified by the task; do not blindly enable every reviewer.

## Regression tests

Use `skills-search/pressure-tests.md` to test changes to this router. Prefer fresh-context runs. When a scenario fails, patch the smallest relevant rule/example and re-run it instead of redesigning the whole workflow.
