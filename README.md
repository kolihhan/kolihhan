<p align="center">
  <img src="./assets/profile-banner.svg" width="100%" alt="Ko Lih Han — Software Engineer, Applied AI and LLM Systems" />
</p>

<p align="center">
  <strong>Building practical AI systems that retrieve, reason, use tools, and survive contact with real software.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-111827?style=for-the-badge&logo=python&logoColor=67E8F9" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-111827?style=for-the-badge&logo=fastapi&logoColor=67E8F9" alt="FastAPI" />
  <img src="https://img.shields.io/badge/LangGraph-111827?style=for-the-badge&logo=langchain&logoColor=A5B4FC" alt="LangGraph" />
  <img src="https://img.shields.io/badge/LLM_Systems-111827?style=for-the-badge&logoColor=D8B4FE" alt="LLM Systems" />
  <img src="https://img.shields.io/badge/RAG-111827?style=for-the-badge&logoColor=67E8F9" alt="RAG" />
  <img src="https://img.shields.io/badge/Agents-111827?style=for-the-badge&logoColor=A5B4FC" alt="Agents" />
</p>

---

## `> about_me`

I'm a software engineer focused on **applied AI, LLM systems, retrieval, agents, and backend engineering**.

I like building systems end to end: retrieval pipelines, tool-using agents, APIs, evaluation harnesses, and the less glamorous parts that make them actually work. Before focusing on AI, I spent several years building and maintaining **Laravel / Vue** applications in production.

Currently finishing my master's at **National Tsing Hua University**, where my research studies how workplace relationships and conversational context affect implicit meaning in dialogue.

## `> featured_projects`

<table>
<tr>
<td width="33%" valign="top">

### 🧠 Semantic Text-to-SQL

Local NL → SQL system with **LangGraph + FastAPI + SQLite**.

Generates SQL, verifies it, executes read-only, and uses a bounded repair loop when execution fails.

**100 BIRD DEV questions**  
`30 → 33` official EX  
`70% → 88%` execution success

<a href="https://github.com/kolihhan/semantic-text2sql-agent"><strong>View repository →</strong></a>

</td>
<td width="33%" valign="top">

### 🔎 Local RAG Search

Hybrid retrieval with **BM25 + Qwen embeddings + reciprocal rank fusion**.

Built as a reusable local search service with CLI, FastAPI, persistent embeddings, and explainable ranking.

**EnterpriseRAG-Bench subset**  
`0.9167` Recall@10  
`0.7986` MRR@20

<a href="https://github.com/kolihhan/local-rag-search"><strong>View repository →</strong></a>

</td>
<td width="33%" valign="top">

### 🎬 Hermes Video Tutor

Multimodal QA agent that decides when to **search transcripts, expand context, inspect frames, or inspect clips**.

Answers keep source evidence, and the agent can abstain when evidence is insufficient.

`Hermes` · `tool use` · `multimodal`  
`local LLM` · `evidence-grounded`

<a href="https://github.com/kolihhan/hermes-video-tutor"><strong>View repository →</strong></a>

</td>
</tr>
</table>

## `> engineering_stack`

<p>
  <img src="https://img.shields.io/badge/Python-0F172A?style=flat-square&logo=python&logoColor=38BDF8" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-0F172A?style=flat-square&logo=fastapi&logoColor=2DD4BF" alt="FastAPI" />
  <img src="https://img.shields.io/badge/PyTorch-0F172A?style=flat-square&logo=pytorch&logoColor=FB7185" alt="PyTorch" />
  <img src="https://img.shields.io/badge/SQLite-0F172A?style=flat-square&logo=sqlite&logoColor=7DD3FC" alt="SQLite" />
  <img src="https://img.shields.io/badge/Docker-0F172A?style=flat-square&logo=docker&logoColor=60A5FA" alt="Docker" />
  <img src="https://img.shields.io/badge/Git-0F172A?style=flat-square&logo=git&logoColor=F97316" alt="Git" />
  <img src="https://img.shields.io/badge/Laravel-0F172A?style=flat-square&logo=laravel&logoColor=FB7185" alt="Laravel" />
  <img src="https://img.shields.io/badge/Vue.js-0F172A?style=flat-square&logo=vuedotjs&logoColor=34D399" alt="Vue.js" />
</p>

```text
AI systems      LLMs · RAG · hybrid retrieval · agents · tool use · evaluation
Backend         Python · FastAPI · REST APIs · SQLite · queues · service design
Web             Laravel · Vue.js · production maintenance · deployments
Engineering     benchmarking · failure analysis · reproducible experiments
```

## `> research`

**Interpreting Implicit Intent through Workplace Hierarchies and Context**  
Studying how workplace relationships and conversational context change the interpretation of implicit meaning in dialogue.

## `> currently_exploring`

🧪 **[Small-Agent QLoRA](https://github.com/kolihhan/small-agent-qlora)** — a controlled local experiment testing whether QLoRA can improve tool selection and tool use in a small Qwen agent. Evaluation is still in progress, so I keep the claims modest.

---

<p align="center">
  <code>build → measure → inspect failures → improve</code>
</p>
