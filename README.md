# Ko Lih Han

Software engineer building applied AI systems around **LLM workflows, retrieval, and tool-using agents**. My projects focus on reproducible evaluation, failure analysis, and the engineering trade-offs behind whether a technique is worth keeping.

I also have production software experience with Laravel/Vue.js, Linux, MySQL, deployments, queue workers, SSL, and server operations.

## Selected work

### [Semantic Text-to-SQL Reliability](https://github.com/kolihhan/semantic-text2sql-agent)
LangGraph Text-to-SQL with deterministic SQL checks, read-only execution, and bounded repair. On 100 BIRD DEV cases, the guarded path raised execution success from **70% to 88%** while official BIRD EX moved from **30% to 33%**; the repo also records the added model-call and latency cost.

### [Local RAG Search](https://github.com/kolihhan/local-rag-search)
Hybrid retrieval with BM25, Qwen dense embeddings, and reciprocal rank fusion behind shared CLI/FastAPI interfaces. On a frozen **12-query EnterpriseRAG-Bench Confluence subset**, RRF reached **0.92 Recall@10 / 0.80 MRR@20** versus **0.75 / 0.55** for BM25.

### [Hermes Video Tutor](https://github.com/kolihhan/hermes-video-tutor)
A multimodal tool-calling agent that searches transcripts and inspects frames or short clips when visual evidence is needed. Hermes chooses the next tool dynamically; evaluation keeps answer correctness, citation validity, modality, and evidence timing separate.

## Research

**M.S. thesis, National Tsing Hua University** — role- and context-aware retrieval for workplace implicit-intent generation. On **401 held-out utterances**, the best role-context fusion improved semantic F1 from **0.625 to 0.689**.

## Experiments

- [**Small-Agent QLoRA**](https://github.com/kolihhan/small-agent-qlora) — local Qwen tool agent with search/read/inspect/python tools, bounded execution, visible traces, deterministic GAIA partitions, and a Base-vs-LoRA evaluation pipeline. The paired QLoRA result is still pending, so no improvement claim is made.

## Main tools

**Python · LangGraph · FastAPI · Ollama · SQLite · BM25 · Dense Retrieval · RRF · pytest**
