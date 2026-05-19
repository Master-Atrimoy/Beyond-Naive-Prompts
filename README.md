# 🧠 Beyond Naive Prompts

***Prompt Engineering Techniques — Beyond Toy Examples***

> ⚙️ Runs 100% locally via Ollama + Mistral — no APIs, no keys, no cloud dependencies.

---

## What this repo is (and isn't)

Most prompt engineering content focuses on:

* summarization
* simple Q&A
* stylistic generation

This repo focuses on something else:

→ **Where prompt engineering actually matters** — ambiguity, reasoning gaps, and failure modes
→ **How to control model behavior**, not just get a correct answer once
→ **Why a technique works**, not just how to apply it

Most prompt engineering content focuses on toy examples like basic summarization or stylistic generation. This repository focuses on production reality:

* 🛠️ **Where prompts break:** Managing ambiguity, unexpected token patterns, and failure modes.
* 🎛️ **Determinism & Control:** Forcing local models to respect hard operational constraints.
* 📊 **Quantifiable Evaluation:** Moving past "vibes" by mathematically scoring outputs locally.

---

## 📁 Repository Directory

| Module                                                                | Purpose                                                                                | Core Stack                         |
| :-------------------------------------------------------------------- | :------------------------------------------------------------------------------------- | :--------------------------------- |
| **[`01_prompt_techniques.ipynb`](./01_prompt_techniques.ipynb)** | 8 applied core prompting patterns using a "Naive vs. Engineered" framework.            | `mistral`                        |
| **[`02_prompt_diff.ipynb`](./02_prompt_diff.ipynb)**             | Automated testing matrix to measure lexical and semantic drift across prompt versions. | `mistral` + `nomic-embed-text` |
| **`03_eval_harness.ipynb`**                                   | *[Coming Soon]* Programmatic LLM-as-a-Judge scoring.                                 | `gemma3` / `llama3.1`          |
| **`04_rag_basics.ipynb`**                                     | *[Coming Soon]* Local contextual retrieval architecture.                             | Local Vector DB                    |

---

## ⚡ Quickstart

### 1. Install & Set Up Ollama

Download and install Ollama from [ollama.com](https://ollama.com). Pull both the generation model and the text-embedding engine:

```bash
ollama pull mistral
ollama pull nomic-embed-text
```

You can also use: **ollama serve**

### 2. Prepare Environment

Install the core playground dependencies, including `rich` for colorized console layouts:

```
pip install requests jupyter rich
```

### 3. Launch

```
jupyter notebook
```

---

## 📓 Module Deep Dives

### Module 01: Core Prompting Techniques (`01_prompt_techniques.ipynb`)

This notebook analyzes exactly *why* a pattern works by directly contrasting a standard

| # | Technique                    | Task                                                       |
| - | ---------------------------- | ---------------------------------------------------------- |
| 1 | **Chain-of-Thought**   | Lateral thinking puzzle — exposes reasoning failure modes |
| 2 | **Few-shot learning**  | Inducing a completely synthetic classification schema      |
| 3 | **Role prompting**     | Same buggy code reviewed under different expert personas   |
| 4 | **Self-consistency**   | Sampling an ethical dilemma to reveal uncertainty          |
| 5 | **Constraint-driven**  | Explaining Transformer attention via strict analogies      |
| 6 | **ReAct reasoning**    | Debugging a CI pipeline with Thought/Action/Observation    |
| 7 | **Prompt chaining**    | Extract → transform pipeline on interview data            |
| 8 | **Negative prompting** | Forcing decisive database recommendations (no hedging)     |

Each section includes:

* 🔴 naive prompt
* 🟢 engineered prompt
* 💡 takeaway (transferable principle)

---

### Why these tasks?

Most examples don't stress the model enough to justify the technique.

These do.

* **Lateral thinking puzzle** → CoT only shows value when reasoning is non-obvious
* **Made-up taxonomy** → few-shot proves induction, not recall
* **Code review personas** → role affects *information surfaced*, not tone
* **Ethical dilemma** → self-consistency exposes uncertainty, not correctness
* **Kitchen analogies** → constraints test understanding vs memorization
* **CI debugging** → ReAct handles branching hypotheses
* **Interview pipeline** → chaining reduces hallucination across steps
* **DB recommendation** → negative prompting counters RLHF hedging

---

### Module 02: Prompt Diff & Semantic Drift (`02_prompt_diff.ipynb`)

When you tweak a prompt template, running it against one test case is an engineering trap. This module builds a testing harness to run prompt updates against an entire evaluation dataset simultaneously.

* **Lexical Delta Mapping:** Leverages Python’s native `difflib` to track absolute textual insertions and deletions line by line.
* **Mathematical Semantic Drift:** Vectors outputs through a local embedding model and computes normalized **Angular Distance** derived from Cosine Similarity:

$$
\text{Semantic Drift} = \frac{\arccos(\text{Cosine Similarity})}{\pi}
$$

* **Interactive Visualization Table:** Automatically color-codes outputs inside the cell and classifies changes ranging from cosmetic formatting tweaks to complete meaning splits.

---

## Roadmap

* [X] `02_prompt_diff.ipynb` — measure semantic shift between prompt variants
* [ ] `03_eval_harness.ipynb` — LLM-as-judge scoring
* [ ] `04_rag_basics.ipynb` — local RAG over personal documents

---

## Philosophy

Prompt engineering isn't a bag of tricks.

It's **interface design for probabilistic reasoning systems**.

---
