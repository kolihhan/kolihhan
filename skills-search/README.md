# Skills Search Router

Use this file before substantive work to choose the smallest correct workflow and discover the right skills at runtime.

## Task routing

| Task signal | Primary mode | File |
|---|---|---|
| research, survey, compare, fact-check, investigate, current state | Research Mode Heavy | `research-mode-heavy.md` |
| build, implement, fix, refactor, debug, ship | Development | `development.md` |
| understand, trace, explain, reverse engineer, old/unfamiliar repo | Repo Understanding | `repo-understanding.md` |
| take over, continue, PIC, execute end-to-end, resume prior work | Claude-like Workflow | `claude-like-workflow.md` |

## Runtime skill discovery

Before execution, search the currently available skill/plugin catalog using task-specific keywords. Prefer installed or reproducibly pinned skills. Never invent a skill or assume an old name is still available.

Load only the skills needed for the task. Do not enable a large suite just because it exists.

If a preferred skill is unavailable, use the closest verified equivalent and continue rather than blocking the task.

## Default combinations

### Research Mode Heavy

Preferred stack when available:

`Superpowers/process control + deep research + primary-source verification + fact-checking + dehallucination/contradiction review + second-pass challenge`

### Development

Default stack:

`Superpowers = main development OS`

`Selected PStack = specialist engineering tools`

`Caveman = concise communication/token layer`

Do not keep PStack FULL permanently enabled.

### Repo Understanding

Default stack:

`Understand Anything + PStack how + Superpowers`

Add persistent codebase-mapping/documentation only when the task actually needs a reusable map.

### Claude-like Workflow

This is the execution behavior layer:

`READ -> ORIENT -> ACT -> VERIFY -> UPDATE SOURCE OF TRUTH -> REPORT`

It can wrap any of the other three modes.

## Composition examples

- Unfamiliar repo + feature: `Claude-like -> Repo Understanding -> Development`
- Research-backed implementation: `Research Mode Heavy -> Development`
- Take over an existing challenge submission: `Claude-like -> Repo Understanding (if needed) -> Development -> final verification`
- Company/job investigation: `Claude-like -> Research Mode Heavy`

## Global quality gate

Before claiming a task is done:

- confirm the requested artifact/action actually exists;
- run the relevant tests/checks or inspect the resulting state;
- cite or point to evidence;
- disclose any unresolved uncertainty or blocker;
- do not convert weak evidence into a strong claim.
