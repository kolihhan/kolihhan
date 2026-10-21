# Skills Search Router

Use this file before substantive work to choose the smallest correct workflow and discover the right skills at runtime.

## Task routing

| Task signal | Primary mode | File |
|---|---|---|
| research, survey, compare, fact-check, investigate, current state | Research Mode Heavy | `research-mode-heavy.md` |
| build, implement, fix, refactor, debug, ship | Development | `development.md` |
| understand, trace, explain, reverse engineer, old/unfamiliar repo | Repo Understanding | `repo-understanding.md` |
| take over, continue, PIC, execute end-to-end, resume prior work | Claude-like Workflow | `claude-like-workflow.md` |
| grill, challenge, red-team, tear apart, prove, stress-test, find blind spots | Grill Mode | `grill-mode.md` |

## Runtime skill discovery

Before execution, search the currently available skill/plugin catalog using task-specific keywords and exact preferred IDs from the relevant mode file.

- Prefer installed or reproducibly pinned skills.
- Treat `discovery_only` catalog entries as candidates, not guaranteed installed capabilities.
- Never invent a skill or assume an old name is still available.
- Load only the skills needed for the task; do not enable a large suite just because it exists.
- If a preferred skill is unavailable, use the closest verified equivalent and continue rather than blocking the task.

## Default combinations

### Research Mode Heavy

Preferred candidates when available:

- `imbad0202/academic-research-skills:deep-research`
- `axiomantic/spellbook:skills/fact-checking`
- `axiomantic/spellbook:skills/dehallucination`
- `axiomantic/spellbook:skills/devils-advocate`
- `cursor/plugins:verify-this`

Use primary/first-party sources and independent verification. See `research-mode-heavy.md`.

### Development

Default stack:

- `obra/superpowers:*` = main development OS
- selected `backnotprop/pstack:*` = specialist engineering tools
- `juliusbrussee/caveman:caveman` = concise communication/token layer when available

Do not keep PStack FULL permanently enabled. See `development.md`.

### Repo Understanding

Preferred candidates when available:

- `egonex-ai/understand-anything:understand`
- `backnotprop/pstack:how`
- relevant `obra/superpowers:*` process/verification skills

Add persistent codebase-mapping/documentation only when the task actually needs a reusable map.

### Claude-like Workflow

This is the execution behavior layer:

`READ -> ORIENT -> ACT -> VERIFY -> UPDATE SOURCE OF TRUTH -> REPORT`

It can wrap the other modes.

### Grill Mode

This is a router to existing adversarial/verification skills, not a separate invented methodology.

Typical core candidates:

- `axiomantic/spellbook:skills/devils-advocate`
- `cursor/plugins:verify-this`

Then add domain-specific reviewers only when warranted. See `grill-mode.md`.

## Composition examples

- Unfamiliar repo + feature: `Claude-like -> Repo Understanding -> Development`
- Research-backed implementation: `Research Mode Heavy -> Development`
- Take over an existing challenge submission: `Claude-like -> Repo Understanding (if needed) -> Development -> final verification`
- Company/job investigation: `Claude-like -> Research Mode Heavy`
- Grill a research conclusion: `Research Mode Heavy -> Grill Mode`
- Grill a code change: `Development -> Grill Mode`
- Grill a spec/plan before execution: `Grill Mode -> Development`

## Global quality gate

Before claiming a task is done:

- confirm the requested artifact/action actually exists;
- run the relevant tests/checks or inspect the resulting state;
- cite or point to evidence;
- disclose any unresolved uncertainty or blocker;
- do not convert weak evidence into a strong claim.
