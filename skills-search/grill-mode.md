# Grill Mode

Use when the user wants scrutiny rather than a supportive first pass: `grill`, `challenge`, `critical review`, `red-team`, `tear apart`, `stress-test`, `prove`, `double-check`, `find blind spots`, or similar.

Grill Mode is a router, not one universal review method. First identify what kind of scrutiny the user actually wants, then load the smallest review/verification path that fits.

## Runtime rule

Search the current skill catalog before invoking third-party skills. Exact IDs below are preferred candidates, not guaranteed installed capabilities.

- Prefer installed or reproducibly pinned skills.
- Treat `discovery_only` entries as candidates that require runtime verification or a verified equivalent.
- Do not enable every reviewer.
- Do not let reviewer volume substitute for source inspection, tests, or primary evidence.

## Route by review intent

### 1. `Grill me` — unresolved plan / decision / idea

Use this when important decisions are still open and the user wants to be questioned until hidden assumptions are exposed.

Preferred candidate:

- `mattpocock/skills:skills/productivity/grilling` — decision-tree interview; facts are researched by the agent, decisions remain with the user.

This is interactive discovery, not an artifact critique. Do not route an already-written report or conclusion here merely because the user used the word `grill`.

### 2. `Critically review this` — existing argument / report / strategy / conclusion

Use this when there is already a stable artifact or conclusion to judge.

Preferred candidate:

- `sammcj/agentic-coding:critical-thinking-logical-reasoning` — steelman the claim, inspect evidence and logic, surface hidden assumptions, alternatives, contradictions, burden of proof, and apply a materiality / `so what` test.

Then verify only the factual claims that materially affect the verdict. Do not manufacture objections to look rigorous; a sound argument may pass.

For an AI-generated answer that may contain invented details, prefer principles or an available equivalent of:

- `mlevison/agent-thinking-skills:critical-thinking-genai` — treat prior model output as an artifact to test, not as evidence about itself; send important checks back to primary sources, files, data, or runtime evidence.
- `axiomantic/spellbook:skills/dehallucination` — check fabricated references, invented capabilities, false constraints, phantom dependencies, and planned-vs-implemented confusion.

### 3. `Prove / verify / double-check this` — falsifiable claim

Use verification rather than adversarial rhetoric when the question can be stated as a measurable claim.

Preferred candidate:

- `cursor/plugins:verify-this` — restate the claim falsifiably, compare baseline/treatment or equivalent evidence, and return `VERIFIED`, `NOT VERIFIED`, or `INCONCLUSIVE`.

For broader technical-claim audits, especially inside research-heavy work, compose with:

- `axiomantic/spellbook:skills/fact-checking`
- Research Mode Heavy

### 4. `Grill this plan/design` — adversarial design review

Use when the artifact is a design, architecture, or implementation plan and the user wants failure-oriented scrutiny rather than an interview.

Preferred candidate:

- `axiomantic/spellbook:skills/devils-advocate` — challenge assumptions, scope, architecture, integrations, success criteria, and failure modes.

Treat its findings as hypotheses to re-check, not requirements. A reviewer objection does not become a design requirement until it survives source/evidence review and is judged material to the user's scope.

For a high-risk spec/plan before implementation:

- `riekelt/multi-agent-review:multi-agent-review` — fail-closed multi-reviewer spec/plan gate.

Do not use a panel for an ordinary low-risk plan.

### 5. `Grill this code` — implementation review

Compose with Development. Start with a single strong reviewer; escalate only when the risk justifies it.

Preferred default:

- `posit-dev/skills:critical-code-reviewer` — correctness, security, failure handling, data/type boundaries, async/concurrency, maintainability, tests, accessibility, and concrete failure modes; distinguish facts, inferences, and questions.

Add only when relevant:

- `Teycir/Assumptions` — evidence-backed ledger of production assumptions, safeguards, consequences, and falsification tests; especially useful for retries, concurrency, transactions, migrations, workers, queues, APIs, and rollout safety.
- `backnotprop/pstack:blast-radius` — trace what a change could break beyond the visible diff and prove the key safety fact with real execution where possible.
- `obra/superpowers:verification-before-completion` — final evidence-before-assertion gate after implementation work.

For `Grill this code HEAVY`:

- `backnotprop/pstack:interrogate` — independent multi-model code review with agreement/disagreement synthesis, when the runtime actually supports the required reviewer models/subagents.

Do not start with multi-model review when one evidence-grounded reviewer plus tests can answer the question.

## Research conclusions

For `Grill this research conclusion`, compose Research Mode Heavy with Critical Review rather than treating skepticism alone as evidence:

1. reconstruct the strongest version of the conclusion;
2. identify material logical/evidentiary weaknesses;
3. check primary evidence and counter-evidence;
4. use fact/dehallucination verification where needed;
5. downgrade to uncertainty when the evidence does not support a strong verdict.

## Maximum-coverage review

When the user explicitly asks for `HEAVY`, `maximum coverage`, `every angle`, or similarly high-cost review and the task genuinely warrants it, choose one strong orchestration path rather than stacking panels.

Preferred broad candidate:

- `wan-huiyan/agent-review-panel:agent-review-panel` — independent reviewers, debate, verification, and judge-based synthesis; suitable for high-stakes code, plans, documents, or mixed artifacts when runtime support exists.

`interrogate` remains the preferred heavy path for code when model diversity is the main value. `multi-agent-review` remains the preferred heavy path for specs/plans when a fail-closed pre-execution gate is the goal.

Do not default to ecosystem-specific or very high-volume red-team frameworks merely because they sound more rigorous. Extra reviewers must increase independent coverage or confidence, not just token use.

## Quick routing

- `Grill me` -> `grilling`.
- `Critically review this` -> logical critical review -> verify material factual claims.
- `Review this AI answer` -> critical-review the output -> primary-source/dehallucination checks.
- `Prove / verify this` -> `verify-this` or closest verified equivalent.
- `Grill this plan/design` -> `devils-advocate`; add `multi-agent-review` only when risk justifies a panel.
- `Grill this research conclusion` -> Research Mode Heavy + critical review + targeted fact/dehallucination verification.
- `Grill this code` -> Development + `critical-code-reviewer`; add `Assumptions` and/or `blast-radius` only for the risks they cover.
- `Grill this code HEAVY` -> `interrogate` + real execution verification when supported.
- `Grill this HEAVY / maximum coverage` -> one justified independent review panel, normally `agent-review-panel`, followed by concrete verification.

## Guardrails

- First understand or steelman the artifact before attacking it.
- Findings must be tied to source evidence, reproducible behavior, concrete reasoning, or explicit uncertainty.
- Separate verified defects from plausible risks, questions, and unknowns.
- Re-check reviewer findings against the actual artifact/source before accepting them.
- Previous AI output, reviewer consensus, confidence, and eloquence are not independent evidence.
- Critique the artifact or reasoning, not the person.
- Do not manufacture criticism; `no material issue found` is a valid result after genuine review.
- Apply the `so what` test: prioritize issues that could change the decision, behavior, correctness, safety, or outcome.
- Do not let a panel replace tests, source inspection, primary evidence, or runtime verification.
- Stop when additional reviewers repeat existing findings without increasing confidence or coverage.
- Respect the scope and irreversible-action baseline in `../AGENTS.md`; review findings do not authorize mutations or external actions.
