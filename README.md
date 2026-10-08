# Ko Lih Han

Software engineer working on **applied AI and backend systems**.

I mostly build with Python and FastAPI, with a focus on retrieval, tool-using agents, local models, and evaluation. Before moving deeper into applied AI, I spent several years building and maintaining Laravel / Vue applications in production.

## Selected projects

### [Semantic Text-to-SQL](https://github.com/kolihhan/semantic-text2sql-agent)

A local Text-to-SQL system with schema grounding, deterministic verification, bounded repair, and read-only execution.

On the current frozen 100-query BIRD DEV slice, guarded verification + repair improved EX-compatible match from **33% to 39%** and conservative execution success from **75% to 90%**.

### [Local RAG Search](https://github.com/kolihhan/local-rag-search)

Hybrid retrieval with BM25, local Qwen embeddings, and reciprocal rank fusion. Results keep BM25, dense, and final fusion ranks visible so failures are easier to inspect.

On a frozen 64-query / 5,189-document slice, hybrid RRF reached **0.7630 Recall@10** and **0.7418 MRR@20**.

### [Hermes Video Tutor](https://github.com/kolihhan/hermes-video-tutor)

A local video QA agent that searches transcripts and decides when it needs to inspect a frame or short clip.

On a small 12-question paired fixture, it reached **66.7% strict full pass on visual-required questions** and used a visual tool on **100%** of those questions.

### [Small-Agent QLoRA](https://github.com/kolihhan/small-agent-qlora)

An experiment on whether QLoRA can improve tool use in a small local agent. The agent runtime, training pipeline, leakage guards, and Base-vs-LoRA comparator are implemented; there is **no valid uplift claim yet**.

## What I work with

**Applied AI:** LLMs, RAG, agents, tool use, multimodal systems  
**Backend:** Python, FastAPI, REST APIs, SQLite, queues  
**Local AI:** Ollama, Qwen, PyTorch  
**Web:** Laravel, Vue.js  
**Engineering:** evaluation, failure analysis, reproducible runs, production debugging

## Background

**M.S., National Tsing Hua University** — research on context-aware implicit meaning in workplace dialogue.

I started in software engineering and production web systems, then moved toward applied AI systems where retrieval quality, tool behavior, and failure modes can be measured directly.
