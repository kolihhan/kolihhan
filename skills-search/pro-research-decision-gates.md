# PRO: Evidence-to-Outcome Research Gates

**PRO is our operational mnemonic**, not a framework attributed to any Kaggle Grandmaster:
**P — Proven failure**, **R — Return on experiment**, **O — Out-of-sample proof**.

Use this after `AGENTS.md` and the selected research/development workflow whenever proposing or continuing an ML/AI experiment, agent training, data-selection change, benchmark variant, or post-training optimization. It complements — never replaces — the router's scope and evidence rules.

## P: Proven failure, not intuition

1. State the **real end metric** first (e.g. strict Text-to-SQL execution match or independent autonomous agent task success), not proxy improvements (SQL validity, training loss, next-action accuracy, checkpoint existence, completion alone).
2. Establish current best **with exact population, model/version, source checksum, run/artifact, and scoring contract**. Label old/invalid, partial, synthetic, and retrospective evidence explicitly.
3. Decompose *paired* failures using preexisting traces: generator candidate absent vs selector error; schema/values/join/grain; wrong tool choice vs search/termination vs environment/format. Distinguish observable failure from assumed cause.
4. State a **falsifiable mechanism**: why one small intervention should correct that failure on *new tasks*, when it should not, and the expected downside. Check oracle/headroom before adding selectors or more candidates.
5. Do not construct examples using protected evaluation answers. Never train or tune on GAIA evaluation or frozen BIRD DEV identifiers.

## R: Return on experiment, not experiment count

Before spending GPU, many model calls, or CI quota, record in the existing PR/issue (no extra tracker):

```text
TARGET         real end-to-end metric and current verified baseline
CAUSE          paired observed failure; alternative explanations
HYPOTHESIS     one change + why it should help + falsifier
POPULATION     frozen task IDs, database/source boundaries, exact model/runtime
CONTROLS       same task, environment, scorer, budgets and unchanged A/A when relevant
GATE           numeric minimum net gain, max regressions, cap on runtime/calls
BUDGET         expected CPU/GPU minutes, calls, source/label availability
REPRODUCE      code commit, inputs SHA, random seeds, exact artifacts
DECISION       GO / REJECT / BLOCKED / INCONCLUSIVE / PROMOTE-CANDIDATE
```

- Prefer **one causal change** over five prompt variants, extra agents, or framework layers. Reuse current code and native tools.
- Freeze cohort and decision threshold **before** generating or scoring. Compare **paired rescues and regressions**, strict primary metric, capability/failure buckets, latency, cost, and significance/uncertainty where meaningful.
- A positive on a public or previously observed development split is only a **screen**; no deployment or resume claim without independent source-, database-, task-, or time-disjoint evaluation.
- If failures cluster in an environment/step-cap issue, separate operational failure from model capability instead of claiming training fixed it.
- A training/evaluation run is not complete until the **physical checkpoint/artifact**, step count, and independent scores have been inspected. A green CI or in-progress GPU job is not proof of improvement.

## O: Out-of-sample proof and stop rules

| Observation | Decision |
| --- | --- |
| No candidate contains the correct answer (oracle/headroom = 0) | Reject selector/reranker/sampling variants on that hypothesis |
| Net primary-metric gain ≤ 0 or unacceptable regressions | Reject and close the experiment unmerged |
| Outcome comes only from easier synthetic or teacher-forced tests | Keep as diagnostic; demand autonomous/real transfer check |
| Only benchmark-known IDs/DBs improved | Mark exploratory, not generalized; freeze new independent cohort first |
| OOD improvement survives, costs acceptable and failure mechanism agrees | Candidate for smallest production change and real execution validation |
| Source, GPU allocation or checkpoint not verified | BLOCKED; do not invent a result or spin up redundant jobs |

After each run, add **one short evidence comment** to its existing PR/issue: exact run, checksum, metric counts, paired rescue/regression, cost, caveats, **decision**. Close rejected experiments rather than leaving speculative branches as active recommendations. Do not opportunistically change the threshold or retrieval rule after reading evaluated labels. Budget a new attempt only for a **new falsifiable mechanism**, not another tune of the same failed proxy.

## Project application

- `semantic-text2sql-agent`: Qwen-only, **no SQL training**. Primary metric: strict semantic execution match on independent physical DBs; SQL execution success is secondary. Use grounded output/projection/filters/joins as failure taxonomy, not gold-derived generation patches.
- `small-agent-qlora`: actual Qwen QLoRA training is permitted; primary metric: independent closed-loop agent success, then matched GAIA generalization. Measure finalization, duplicate calls, failure recovery, horizon length and tool budgets separately. Teacher-forced next-action probes are diagnostic only.
- `name-kaggle` and `gemma-4-kaggle`: independently validate complementary signal or agent-budget gains before fusion/promotion; never optimize only against a public leaderboard slice.

**Do not claim this method itself improved a score.** It governs decisions; measured model gains still require completed experiments.
