# Ko Lih Han

**Software Engineer · Applied AI / Backend**

I build applied AI systems around measurable failure modes — retrieval, tool use, SQL generation, multimodal QA, and post-training. I care about whether a system actually improves under a frozen evaluation, not just whether the demo works.

## Selected work

### [Small-Agent QLoRA](https://github.com/kolihhan/small-agent-qlora)

Post-training a Qwen3.5-9B tool agent with targeted QLoRA/SFT, controlled evaluation, and matched external validation.

**34.5% → 52.5% → 62.0%** controlled closed-loop exact success  
**9% → 18% → 18%** matched GAIA100

The final corrective stage improved the controlled policy but exposed an over-search / failure-to-finalize weakness on longer GAIA trajectories.

### [Semantic Text-to-SQL](https://github.com/kolihhan/semantic-text2sql-agent)

Local NL → SQL with schema grounding, deterministic verification, bounded repair, and read-only execution.

**33% → 39%** BIRD EX-compatible match · **75% → 90%** conservative execution success  
<sub>Frozen 100-query BIRD DEV slice</sub>

## How I build

`baseline → measure → inspect failures → smallest useful change → measure again`

**Applied AI** — LLMs, RAG, agents, tool use, multimodal systems, post-training  
**Evaluation** — retrieval metrics, paired experiments, failure analysis, reproducible runs  
**Backend** — Python, FastAPI, SQLite, APIs, queues, service boundaries  
**Production** — Laravel, Vue.js, deployments, maintenance, operational debugging

## Background

**M.S., National Tsing Hua University** — research on context-aware implicit meaning in workplace dialogue.

Software engineering background in production web systems, backend workflows, deployment, and maintenance.
