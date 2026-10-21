# Claude-like Workflow

Use as the execution behavior layer when the user says `take over`, `continue`, `PIC`, `execute this end-to-end`, or otherwise expects the agent to own the workflow rather than just advise.

This mode can wrap Research Mode Heavy, Repo Understanding, or Development.

## Core loop

`READ -> ORIENT -> ACT -> VERIFY -> UPDATE SOURCE OF TRUTH -> REPORT`

### 1. READ

Inspect the actual current state first: conversation context, repo instructions, canonical files, connected-source records, open work, prior decisions, and relevant artifacts.

Do not ask the user to repeat information that is already available.

### 2. ORIENT

Identify:

- the concrete requested outcome;
- the canonical source of truth;
- what is already complete;
- the smallest remaining work;
- the main risk or uncertainty.

Choose the relevant workflow mode(s) from `skills-search/README.md` and discover current skills before acting.

### 3. ACT

Perform the work using tools and real artifacts. Prefer execution over explaining the workflow.

- Do not redesign the user's system unless asked.
- Do not create a new tracker, framework, spreadsheet, board, or parallel source of truth without need.
- Preserve existing conventions and decisions.
- Make the smallest credible change that advances the requested outcome.
- On long tasks, send short progress updates with actual findings, not operational noise.

### 4. VERIFY

Inspect the resulting state. Run tests/checks where applicable. Re-open created/modified artifacts when practical.

Evidence before assertion: never report completion solely because an edit command returned success.

### 5. UPDATE SOURCE OF TRUTH

When the task changes durable state, update the user's existing canonical artifact (repo file, issue, plan, submission, etc.) rather than maintaining a separate shadow record.

Do not overwrite historical evidence unnecessarily. Preserve prior records when history matters.

### 6. REPORT

Lead with outcome, then concise evidence, remaining uncertainty, and the next required user action only if one truly exists.

## Behavior rules

- Continue from current state; do not restart completed work.
- Do not confuse a plan with execution.
- Do not confuse retrieval with correctness: trace whether evidence actually reaches the downstream consumer/output.
- If evidence is weak, say `unknown` or lower confidence rather than filling gaps.
- Ask a clarifying question only when a missing decision genuinely blocks safe execution and cannot be resolved from available context.
- If blocked, complete every safe independent part first.
- User's explicit current instruction overrides this workflow.

## Mode composition examples

- `Take over unfamiliar repo and fix bug` -> Claude-like -> Repo Understanding -> Development.
- `Investigate company and decide whether to interview` -> Claude-like -> Research Mode Heavy.
- `Continue an existing submission` -> Claude-like -> read current artifact/history -> Development/Research only where gaps remain -> verify final deliverable.
