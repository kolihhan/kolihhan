# PRO research playbook — discover breakthroughs, not merely reject experiments

**PRO here means professional-grade research practice**, not a named method created or endorsed by Yuanzhe Zhou or any other Grandmaster. This playbook applies to ML competitions, LLM agents, Text-to-SQL and research engineering.

**Purpose:** continuously discover *new, transferable capability* that changes the real end metric. Stop gates, reproducibility and cost control are supporting tools, **not the research strategy**. A negative small experiment rejects a specific implementation on a specific population; it does **not** automatically reject its entire hypothesis family.

## Lessons grounded in actual winning write-ups

- **LLM Prompt Recovery, fifth place (Zhou / Zeng / Abulkhanov):** compared prompt distributions, constructed ~500k training samples, combined learned representations, embedding retrieval, Mistral-generated candidates and reranking. Crucially, they inspected the concrete T5 tokenizer behavior when a seemingly clever token trick failed to transfer to the leaderboard. *Lesson:* design several components that address different information bottlenecks; investigate distribution/implementation mismatches rather than keep tuning one score.
  - Primary source: https://www.kaggle.com/competitions/llm-prompt-recovery/writeups/z-d-z-5th-place-solution
- **CMI sensor challenge, winning-team write-up:** used signal preprocessing, features and input orientation/subject effects plus ensemble diversity rather than one mandatory fashionable model. *Lesson:* find task/data structure that the original system is not representing.
  - Primary source: https://www.kaggle.com/competitions/cmi-detect-behavior-with-sensor-data/writeups/cmi-1st-place-solution
- **Other Kaggle Grandmasters:** domain/data exploration, validation design, shift checks, feature engineering and quick iteration are repeated themes; they are not a guarantee of any individual win.
  - Source: https://developer.nvidia.com/blog/kaggle-grandmasters-unveil-winning-strategies-for-data-science-superpowers/

These are **examples to reason from, not recipes or claims of a universal method**.

## The operating loop: UNDERSTAND → INVENT → TEST → LEARN → TRANSFER → REPEAT

### 1. Understand the *information and capability bottleneck*

Read the actual task contract, metric, constraints, data families, schema/trajectory structure, train/eval shift and physical runtime before inventing code. Study top methods **and their failures**, alongside simple baselines.

For each failure, ask whether the model lacked **input evidence**, **the right representation**, **candidate-generation capability**, **a decision policy**, or **a reliable execution environment**. Use paired error traces, retrieval headroom and oracle diagnostics when they distinguish causes. Do not confuse a plausible story with a confirmed causal attribution.

### 2. Invent multiple *different* mechanisms before choosing one

Write a small **idea portfolio**, then select the highest-information, highest-upside feasible idea:

| Search lane | Example mechanism | What new ability/information would it supply? |
| --- | --- | --- |
| Data/evidence | Schema-value grounding, source-reliable observations, harder real tool traces | Answer based on previously missing facts |
| Representation | Relational structure, role/entity reasoning, task-state abstraction | Express relationships not exposed by the baseline |
| Learning/policy | Better supervised action targets, long-horizon recover/finalize states, distillation from verified traces | Choose actions based on changing state, not memorized shortcuts |
| Complementary systems | Independent retrieval, verification, candidate generation, ranking **if headroom exists** | Recover different failures rather than repeat the same errors |

Select by **failure coverage × plausible transfer × evidence availability ÷ compute/engineering cost**. This is a prioritization heuristic, not a fabricated numerical formula. A small cheap *mechanism diagnostic* can outrank a costly full run. When all current ideas fail, **go back to source/task research and generate a different hypothesis**, not simply stop working.

### 3. Test mechanisms, not just final scores

Use the smallest controlled experiment that can distinguish your explanation from competing explanations: frozen comparator, same source/model/tool budget, A/A stability where needed, paired correct→wrong/wrong→correct, costs, and a *mechanism-level observable* (e.g., target column present, evidence retrieved, last-step finalization after tool failure).

**Use a ladder:** cheap deterministic probe → task/source-diverse paired pilot → autonomous end-to-end validation → independent population/physical-DB transfer. Avoid deciding broad hypotheses from 16–20 samples as if they had high statistical power. Choose the numerical promotion gate **for that experiment's uncertainty and costs**, not a universal +3/20 threshold.

### 4. Extract *information* from every experiment

After a negative result, ask:

1. Was the mechanism actually delivered to the model/agent? (e.g. retrieved useful evidence vs noisy examples; supervised end states vs empty labels)
2. Did its intermediate behavior change as predicted? If no, fix the mechanism/test; if yes but final score did not, inspect downstream bottlenecks and regressions.
3. Was there *any reachable correct candidate* or *independent rescue*? Does the method add complementary signal or merely duplicate baseline outputs?
4. Could evaluation noise, dataset/source mismatch, task hardness, model limitations or environment failure explain the result?
5. **Next decision:** revise a genuinely changed mechanism, combine independently complementary signals, pursue a different lane, or shelve *this concrete candidate*. Preserve the negative result without imposing a permanent ban on the entire field.

Keep the source-of-truth PR/issue short: **observation → causal alternatives → new belief → next decisive test**. Do not create endless process documents, fake conclusions, or repetitive tune loops.

### 5. Transfer and integrate only earned gains

- A win on synthetic/teacher-forced/public data is a **diagnostic or screen**, not evidence of real generalization.
- Check source-, task-, database-, time-, or model-distribution shifts as relevant and disclose possible contamination/pretraining.
- Measure **coverage, rescues, regressions, complementarity and cost** before ensembling/reranking. A correct-answer oracle with zero extra headroom says **don't optimize the selector**; try to create better candidates or better evidence.
- Keep a mechanism only if independent closed-loop/strict primary metrics improve at acceptable cost. Don't obscure failure modes behind aggregate averages.
- Continue the next high-upside research lane independently if another run is blocked by GPU/service quota; don't pretend a pending job is progress.

## A compact work order (use an existing PR/issue, no new tracker)

```text
GOAL      Real metric and current verified baseline; evaluation limitations
INSIGHT   Specific error pattern + competing explanations
IDEAS     2-3 distinct mechanisms; select one with highest information/expected gain per cost
PROBE     What would prove the mechanism is functioning (before full model spend)?
TEST      Comparison cohort, source independence, paired metrics, budget/stop rule
RESULT    Physical artifact, score + confidence, rescues/regressions, per-group effects
LEARNING  What we know now that we didn't know before
NEXT      One new decisive action: improve mechanism / combine / pivot / transfer / stop candidate
```

**Project constraints:** Text-to-SQL stays **Qwen-only with no SQL model training**; QLoRA uses **real Qwen training** with no GAIA evaluation-data supervision. Never claim GPU progress without physical adapter/steps; never claim strict semantic correctness from SQL execution success. No benchmark-driven patching, leakage or fake independent transfer.

**Success of this playbook is not the number of rejected PRs.** It is the quality of new hypotheses, information gained per experiment, and verified improvement on the project's real outcome.
