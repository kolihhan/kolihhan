# Grill Mode

Use when the user asks to `grill`, `challenge`, `red-team`, `tear apart`, `stress-test`, `prove`, `double-check`, `find blind spots`, or otherwise wants an adversarial review rather than a supportive first-pass answer.

Grill Mode is a router to existing review/verification skills. It does not invent a separate methodology when a strong existing skill already covers the task.

## Runtime rule

Search the current skill catalog first. Exact IDs below are preferred candidates, not permanent assumptions. Prefer installed or reproducibly pinned skills; treat `discovery_only` entries as candidates that may need a verified equivalent.

Do not enable every reviewer. Pick the smallest set that covers the actual risk.

## Core candidates

### General claim / decision challenge

- `axiomantic/spellbook:skills/devils-advocate` — challenge assumptions, risks, weaknesses, and hidden premises.
- `cursor/plugins:verify-this` — verify a falsifiable claim with fresh evidence and return VERIFIED / NOT VERIFIED / INCONCLUSIVE.

Default `Grill this` should usually start here.

### Research / factual claims

Compose with Research Mode Heavy when needed:

- `axiomantic/spellbook:skills/fact-checking`
- `axiomantic/spellbook:skills/dehallucination`
- `imbad0202/academic-research-skills:deep-research`

Use these for claim verification, source reality checks, counter-evidence, and high-stakes research conclusions.

### Code / implementation

Compose with Development when needed:

- `backnotprop/pstack:interrogate` — multi-angle / multi-model adversarial review.
- `backnotprop/pstack:blast-radius` — find what a change could break beyond the visible diff and prove a key safety fact with real execution.
- `ArabelaTso/Skills-4-SE:skills/edge-case-generator` — generate boundary and exception cases for code/APIs.
- `obra/superpowers:verification-before-completion` — final evidence-before-assertion gate.

For a zero-base final implementation audit, `openai/openai-agents-python:.agents/skills/implementation-final-review` is a strong candidate, but obey its own trigger contract: use it only when explicitly invoked by the user or when repository instructions authorize automatic invocation.

### Spec / plan before implementation

- `riekelt/multi-agent-review:multi-agent-review` — multi-reviewer fail-closed review for specs/plans before execution.

Use this for high-risk specs/plans, not ordinary code review.

### High-stakes broad adversarial review

Choose one strong orchestration path when ordinary Grill is insufficient:

- `danielmiessler/LifeOS:LifeOS/install/skills/RedTeam` — attack/steelman/counter-argue ideas, strategies, plans, and major conclusions.
- `wan-huiyan/agent-review-panel:agent-review-panel` — multiple independent reviewer perspectives with debate/judgment; supports deeper review modes.

Normally choose one, not both. Add both only when the user explicitly wants maximum-cost/max-coverage review and the runtime actually supports them.

## Suggested routing

- `Grill this` -> `devils-advocate` + `verify-this` when available.
- `Grill this research conclusion` -> Research Mode Heavy + `devils-advocate` + fact/dehallucination verification.
- `Grill this code` -> Development + `interrogate` + `blast-radius`; add edge cases when relevant.
- `Grill this spec/plan` -> `multi-agent-review` when risk justifies a panel.
- `Grill this HEAVY` -> choose the strongest justified independent/adversarial review path for the artifact type, then finish with concrete verification.

## Guardrails

- Findings must be tied to evidence, reproducible behavior, concrete reasoning, or an explicit uncertainty.
- Do not manufacture objections just to appear critical.
- Separate confirmed defects from plausible risks and unverified concerns.
- Re-check reviewer findings against the actual artifact/source before accepting them.
- Do not let a review panel replace tests, source inspection, or primary evidence.
- Stop when additional reviewers are only repeating the same finding without increasing confidence or coverage.
