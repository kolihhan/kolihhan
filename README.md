<div align="center">

# kolihhan

### Building AI systems that can be tested, inspected, and improved.

Local models · Retrieval · Tool-using agents · Evaluation

[Explore my work](#selected-projects) · [How I build](#engineering-approach)

</div>

---

I build practical AI applications with Python, from SQL verification and hybrid search to multimodal tutoring and small-model agents. My focus is the full loop: build a working system, compare it against a baseline, and understand where it fails.

## Selected projects

<table>
<tr>
<td width="50%" valign="top">

### 01 / Text-to-SQL Reliability

**Can a verifier make generated SQL more reliable?**

A LangGraph workflow combining local SQL generation, read-only SQLite checks, and bounded repair. Paired BIRD evaluations separate execution success from answer correctness.

`Python` `LangGraph` `SQLite` `Ollama`

[Explore the project →](https://github.com/kolihhan/semantic-text2sql-agent)

</td>
<td width="50%" valign="top">

### 02 / Local RAG Search

**When does hybrid retrieval help?**

BM25 and Qwen embeddings combined with reciprocal rank fusion. Includes a CLI, API, and paired retrieval evaluation with recall, ranking, and latency measurements.

`Python` `BM25` `Embeddings` `RRF`

[Explore the project →](https://github.com/kolihhan/local-rag-search)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 03 / Hermes Video Tutor

**What does a transcript miss?**

A tutor that searches transcripts and inspects frames or clips to answer with evidence. A small synthetic paired evaluation examines when visual tools help.

`Python` `Hermes` `Multimodal` `Streamlit`

[Explore the project →](https://github.com/kolihhan/hermes-video-tutor)

</td>
<td width="50%" valign="top">

### 04 / Small-Agent QLoRA

**Can verified trajectories improve a small tool agent?**

A local Qwen agent with search, read, inspect, and Python tools, plus a controlled QLoRA experiment pipeline. The current experiment is limited by local hardware resources.

`Python` `Qwen` `QLoRA` `Tool use`

[Explore the project →](https://github.com/kolihhan/small-agent-qlora)

</td>
</tr>
</table>

## Engineering approach

- **Start with a baseline.** Measure what added complexity actually buys.
- **Make behavior inspectable.** Keep tool traces, evidence, and evaluation artifacts.
- **Report the tradeoffs.** Accuracy, latency, model calls, and resource limits all matter.
- **Keep claims proportional to evidence.** Small fixtures and negative results have a place.

---

<div align="center">
<sub>Reliable behavior starts with a measurable question.</sub>
</div>
