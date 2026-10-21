# Agent Workflow Router

This repository is the personal default source of truth for how agents should approach substantive work for Ko Lih Han.

## Before any substantive task

1. Read `skills-search/README.md`.
2. Classify the task into one or more workflow modes.
3. Read the relevant mode file(s).
4. Discover and verify the currently available skills/plugins for that mode. Do not rely on stale skill names from memory.
5. Execute the actual task. Do not stop at methodology, planning, or commentary unless that is the requested deliverable.
6. Verify with evidence before claiming completion.

## Precedence

Current explicit user instruction > target repository's local `AGENTS.md` / project rules > task-specific workflow mode > this personal default.

When working in another repository, inspect and respect that repository's own instructions first. Use this router only where it does not conflict.

## Default behavior

- Use the shortest credible path.
- Reuse the canonical source of truth; do not create parallel trackers/frameworks unless explicitly requested.
- Do not ask for information already available in the conversation, repository, files, or connected sources.
- Separate facts, inference, and unknowns.
- Prefer primary evidence and real execution over confident narration.
- For long tasks, keep progress updates short and useful.
- Report results first, then only the evidence needed to support them.

## Mode composition

Modes may compose. Example:

`Take over unfamiliar repo + implement feature` -> Claude-like Workflow -> Repo Understanding -> Development.

`Research a technical choice + implement it` -> Research Mode Heavy -> Development.
