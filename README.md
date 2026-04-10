# LLM Benchmark — Round-Robin Judge Edition

> "Bigger model = better output." I tested that assumption. It didn't survive.

A fully local LLM benchmarking system that measures **speed + quality** across three open-source models — with zero API costs, zero internet, and zero self-judging.

---

## What This Does

1. Sends the same 4 prompts to 3 local models (Llama, Mistral, Phi-3)
2. Measures response speed (latency in ms) per model
3. Has each model judge the other two — never itself (Round-Robin)
4. Aggregates scores into a final leaderboard
5. Visualises results via heatmap, delta chart, and radar chart

---

## Why Round-Robin?

If Mistral judges Mistral, that's not an evaluation. That's a mirror.

Each model scores its peers on:
- **Accuracy** (out of 10)
- **Clarity** (out of 10)
- **Completeness** (out of 10)

Every response gets exactly 2 independent judges.
Final score = average of both.

---

## Results Summary

| Model | Avg Latency | Notable Delta |
|---|---|---|
| llama3.2:3b | ~6,990ms | +0.33 on EV prompt (best overall) |
| mistral:7b | ~10,058ms | -0.17 on EV prompt |
| phi3:mini | ~8,285ms | -0.33 on ML definition |

> The smallest model outperformed both larger ones on the hardest task.

---

## Tech Stack

| Tool | Role |
|---|---|
| Python | Core logic |
| Ollama | Local model serving (localhost:11434) |
| Pandas | Data aggregation |
| Plotly Express | Interactive charts |
| Jupyter Notebook | Development environment |

---

## Setup & Run

### Prerequisites
- Ollama installed and running
- Python 3.9+
