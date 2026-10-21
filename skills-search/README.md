# Skills Search Router

Use this file once at substantive task entry to choose the smallest correct workflow. Exact preferred skill IDs live in the relevant mode file, not here.

## Task routing

In ordinary chat sessions, **Claude-like Workflow is the default outer layer for every substantive task**. Then add the relevant inner mode(s) below.

| Task signal | Mode | File |
|---|---|---|
| ordinary-chat substantive task; take over, continue, PIC, execute end-to-end, resume prior work | Claude-like Workflow (outer layer) | `claude-like-workflow.md` |
| research, survey, compare, fact-check, investigate, current state | Research Mode Heavy | `research-mode-heavy.md` |
| build, implement, fix, refactor, debug, ship | Development | `development.md` |
| understand, trace, explain, reverse engineer, old/unfamiliar repo | Repo Understanding | `repo-understanding.md` |
| grill, challenge, red-team, tear apart, prove, stress-test, find blind spots | Grill Mode | `grill-mode.md` |

Simple single-step, read-only, no-side-effect requests may bypass this router under the root `AGENTS.md` threshold.

## Routing rule

Classify once, then compose modes as needed.

Claude-like Workflow is an outer execution layer, not a reason to route again. After it selects the relevant inner mode(s), continue execution without returning to this README unless the user's task materially changes.

Bad: `Claude-like -> ORIENT -> read README -> Claude-like -> ORIENT -> read README ...`

Good: `Read README once -> Claude-like outer layer -> Repo Understanding -> Development -> execute/verify/report.`

## Runtime skill discovery

After routing, read the selected mode file(s) and discover/verify the currently available skills/plugins there.

- Prefer installed or reproducibly pinned skills.
- Treat `discovery_only` catalog entries as candidates, not guaranteed installed capabilities.
- Never invent a skill or assume an old name is still available.
- Load only the skills needed for the task; do not enable a large suite just because it exists.
- If a preferred skill is unavailable, use the closest verified equivalent and continue rather than blocking the task.

## Mode roles

- **Claude-like Workflow** — default outer execution layer for substantive ordinary-chat work and explicit take-over/PIC/end-to-end tasks. See `claude-like-workflow.md`.
- **Research Mode Heavy** — high-stakes evidence gathering, verification, counter-evidence, and uncertainty handling. See `research-mode-heavy.md`.
- **Development** — implementation/debugging with the smallest sufficient engineering process. See `development.md`.
- **Repo Understanding** — reconstruct unfamiliar code from source, runtime flow, tests, and history. See `repo-understanding.md`.
- **Grill Mode** — adversarial review router using existing verification/reviewer skills. See `grill-mode.md`.

## Composition examples

- Ordinary chat + consequential research: `Claude-like -> Research Mode Heavy`
- Unfamiliar repo + feature: `Claude-like -> Repo Understanding -> Development`
- Research-backed implementation: `Claude-like -> Research Mode Heavy -> Development`
- Take over an existing challenge submission: `Claude-like -> Repo Understanding (if needed) -> Development -> final verification`
- Company/job investigation: `Claude-like -> Research Mode Heavy`
- Grill a research conclusion: `Claude-like -> Research Mode Heavy -> Grill Mode`
- Grill a code change: `Claude-like -> Development -> Grill Mode`
- Grill a spec/plan before execution: `Claude-like -> Grill Mode -> Development`

## Global behavior

Global precedence, scope/irreversible-action rules, evidence/reporting rules, and compression safety are defined canonically in `../AGENTS.md`. Mode files and third-party skills should point back to those rules rather than duplicate or weaken them.

## Router regression tests

Use `pressure-tests.md` after changing routing, scope, verification, reporting, or safety behavior. Prefer fresh-context runs; patch the smallest failed rule rather than adding broad new process.
