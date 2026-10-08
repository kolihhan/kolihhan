# Ko Lih Han

**Software Engineer · Applied AI / Backend**

<sub>Python · FastAPI · Retrieval · Agents · Evaluation · Local LLMs</sub>

I build applied AI and backend systems with a focus on retrieval quality, tool behavior, and measurable failure modes. Before moving deeper into AI, I spent several years building and maintaining Laravel / Vue applications in production.

---

## Selected projects

### [Semantic Text-to-SQL](https://github.com/kolihhan/semantic-text2sql-agent)

Local NL → SQL with schema grounding, deterministic verification, bounded repair, and read-only execution.

**33% → 39%** EX-compatible match · **75% → 90%** conservative execution success  
<sub>Frozen 100-query BIRD DEV slice · [View repository →](https://github.com/kolihhan/semantic-text2sql-agent)</sub>

### [Local RAG Search](https://github.com/kolihhan/local-rag-search)

Hybrid retrieval with BM25, local Qwen embeddings, and reciprocal rank fusion with visible rank provenance.

**0.7630** Recall@10 · **0.7418** MRR@20 · **0.8438** Hit@10  
<sub>Frozen 64-query / 5,189-document slice · [View repository →](https://github.com/kolihhan/local-rag-search)</sub>

### [Hermes Video Tutor](https://github.com/kolihhan/hermes-video-tutor)

A local video QA agent that searches transcripts and decides when it needs to inspect a frame or short clip.

**66.7%** visual-required strict full pass · **100%** visual-tool use on visual questions  
<sub>Small 12-question paired fixture · [View repository →](https://github.com/kolihhan/hermes-video-tutor)</sub>

### [Small-Agent QLoRA](https://github.com/kolihhan/small-agent-qlora)

An experiment on whether QLoRA can improve tool use in a small local agent.

**Status:** experiment infrastructure is implemented; there is **no valid Base-vs-LoRA uplift claim yet**.  
<sub>[View repository →](https://github.com/kolihhan/small-agent-qlora)</sub>

---

## Stack

`Python` `FastAPI` `PyTorch` `Ollama` `SQLite` `Laravel` `Vue.js`

**Applied AI** — LLMs, RAG, agents, tool use, multimodal systems  
**Engineering** — evaluation, failure analysis, reproducible runs, production debugging

## Background

**M.S., National Tsing Hua University** — research on context-aware implicit meaning in workplace dialogue.

Software engineering background in production web systems, backend workflows, deployment, and maintenance.
