# Ko Lih Han

Software engineer working on applied AI and backend systems.

I mostly build with Python, LLMs, retrieval, agents, and APIs. I also have several years of experience building and maintaining Laravel/Vue applications in production, including deployments, queues, databases, and server issues.

## Projects

### [Semantic Text-to-SQL](https://github.com/kolihhan/semantic-text2sql-agent)
A local Text-to-SQL service built with LangGraph, FastAPI, and SQLite. It validates generated SQL, runs queries read-only, and can retry failed queries using the database error. On 100 BIRD DEV questions, execution success went from **70% to 88%**; official EX went from **30% to 33%**.

### [Local RAG Search](https://github.com/kolihhan/local-rag-search)
Hybrid search with BM25, Qwen embeddings, and reciprocal rank fusion, available through a CLI and FastAPI. On a 12-query EnterpriseRAG-Bench subset, RRF reached **0.92 Recall@10** and **0.80 MRR@20**, compared with **0.75** and **0.55** for BM25.

### [Hermes Video Tutor](https://github.com/kolihhan/hermes-video-tutor)
A video QA agent that can search transcripts and look at frames or short clips. The model decides which tool to use based on the question and keeps source evidence with the answer.

## Master's research

**Interpreting Implicit Intent through Workplace Hierarchies and Context** — studied how workplace relationships and conversational context affect implicit meaning in workplace dialogue.

## Other work

[**Small-Agent QLoRA**](https://github.com/kolihhan/small-agent-qlora) is a work-in-progress local tool agent. I'm using it to test whether QLoRA can help a small Qwen model choose and use tools more reliably. The Base vs LoRA comparison is not finished yet.
