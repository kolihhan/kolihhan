# Ko Lih Han

Software engineer working on applied AI systems around **tool-using agents, retrieval, and reliable LLM workflows**. I care about reproducible evaluation, failure analysis, and the engineering trade-offs behind whether a technique is worth keeping.

My software background also includes production web systems with Laravel/Vue.js, Linux, MySQL, deployments, queue workers, SSL, and server operations.

## Selected work

- [**Semantic Text-to-SQL Reliability**](https://github.com/kolihhan/semantic-text2sql-agent) — LangGraph Text-to-SQL with deterministic SQL checks, read-only execution, and bounded repair. On 100 BIRD DEV cases, the guarded path improved execution success from **70% to 88%**; official BIRD EX moved from **30% to 33%**, with the added model-call and latency cost documented in the repo.
- [**Local RAG Search**](https://github.com/kolihhan/local-rag-search) — Hybrid retrieval with BM25, Qwen dense embeddings, and reciprocal rank fusion behind shared CLI/FastAPI interfaces. On a frozen 12-query EnterpriseRAG-Bench Confluence subset, RRF reached **0.92 Recall@10 / 0.80 MRR@20** versus **0.75 / 0.55** for BM25.
- [**Hermes Video Tutor**](https://github.com/kolihhan/hermes-video-tutor) — A Hermes tool-calling agent that searches transcripts and inspects frames or clips when visual evidence is needed. Evaluation separates answer correctness, citation validity, modality, and evidence timing; the review-v2 live rerun is still pending.
- [**Small-Agent QLoRA**](https://github.com/kolihhan/small-agent-qlora) — A local Qwen tool agent with search/read/inspect/python tools, bounded execution, duplicate-call blocking, visible traces, deterministic GAIA partitions, and a Base-vs-LoRA evaluation pipeline. No QLoRA improvement claim is made until a valid paired run completes.

## Research

**M.S. thesis, National Tsing Hua University** — role- and context-aware retrieval for workplace implicit-intent generation. On **401 held-out utterances**, the best role-context fusion improved semantic F1 from **0.625 to 0.689**.

## Main tools

**Python · LangGraph · FastAPI · Ollama · SQLite · BM25 · Dense Retrieval · RRF · pytest**
