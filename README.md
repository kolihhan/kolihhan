<p align="center">
  <img src="./assets/profile-banner.svg" width="100%" alt="Ko Lih Han — Software Engineer, Applied AI and LLM Systems" />
</p>

<p align="center">
  <strong>Software engineer building applied AI systems that retrieve, reason, use tools, and fail visibly.</strong>
</p>

<p align="center">
  <code>Python · FastAPI · local LLMs · retrieval · agents · evaluation · backend systems</code>
</p>

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,fastapi,pytorch,docker,git,sqlite,vue,laravel&perline=8" alt="Python, FastAPI, PyTorch, Docker, Git, SQLite, Vue, Laravel" />
</p>

---

## About

I build **applied AI systems around real failure modes** — weak retrieval, wrong SQL that still executes, unnecessary multimodal calls, and small agents that use tools poorly.

My projects usually start with a simple local baseline, measure where it breaks, then add the smallest mechanism that improves the system: **retrieval fusion, deterministic verification, semantic revision, or adaptive tool use**. Before focusing on AI, I also spent several years building and maintaining Laravel / Vue applications in production.

## Selected work

Four projects, four different reliability problems.

<table>
<tr>
<td width="50%" valign="top">

### 🧠 Semantic Text-to-SQL

**Problem** — executable SQL can still answer the wrong question.

**Mechanism** — clause-guided semantic revision, deterministic verification, bounded repair, read-only execution.

**Measured baseline** — frozen 100-query BIRD DEV slice:  
`63% → 82%` execution success  
`31% → 34%` official EX

<sub>Measured numbers predate CGSR; the semantic layer is evaluated separately.</sub>

<a href="https://github.com/kolihhan/semantic-text2sql-agent"><strong>View project →</strong></a>

</td>
<td width="50%" valign="top">

### 🔎 Local RAG Search

**Problem** — lexical and dense retrieval fail in different ways.

**Mechanism** — BM25 + local Qwen dense retrieval + reciprocal rank fusion with rank provenance.

**Frozen 64-query / 5,189-doc slice**  
`0.7630` Recall@10  
`0.7418` MRR@20

<a href="https://github.com/kolihhan/local-rag-search"><strong>View project →</strong></a>

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🎬 Hermes Video Tutor

**Problem** — transcript-only QA misses visual evidence; always using vision is wasteful.

**Mechanism** — a local agent decides whether transcript evidence is enough or whether to inspect a frame / clip.

**12-case paired fixture**  
`66.7%` visual-required full pass  
`100%` visual-tool use on visual questions

<sub>Small self-authored product evaluation, not a broad video-QA benchmark.</sub>

<a href="https://github.com/kolihhan/hermes-video-tutor"><strong>View project →</strong></a>

</td>
<td width="50%" valign="top">

### 🧪 Small-Agent QLoRA

**Question** — can QLoRA make a local 4B tool agent use search, files, inspection, and Python more reliably?

**Mechanism** — bounded single-model agent loop, trajectory collection, leakage guards, QLoRA training path, and Base-vs-LoRA comparator.

**Status** — experiment infrastructure is implemented; there is **no valid LoRA uplift claim yet**.

<a href="https://github.com/kolihhan/small-agent-qlora"><strong>View experiment →</strong></a>

</td>
</tr>
</table>

## How I build

```text
build a baseline → measure it → inspect failures → add the smallest useful mechanism → measure again
```

| Area | What I care about |
|---|---|
| **Applied AI** | LLMs, RAG, agents, tool use, multimodal systems |
| **Evaluation** | paired experiments, failure analysis, reproducible runs |
| **Backend** | Python, FastAPI, REST APIs, SQLite, queues, service boundaries |
| **Production** | Laravel, Vue.js, deployments, maintenance, operational debugging |

## Background

**M.S., National Tsing Hua University** — research on context-aware implicit meaning in workplace dialogue.  
**Software engineering** — production web systems, backend workflows, deployments, and maintenance before moving deeper into applied AI.

---

<p align="center">
  <code>build → measure → inspect failures → improve</code>
</p>
