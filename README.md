# 🧠 Prompt Engineering Techniques — Beyond Toy Examples

> * [ ] 
>
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

---

## What's inside

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

## Quickstart

```bash
# 1. Install Ollama — https://ollama.com
ollama pull mistral

# 2. Install dependencies
pip install requests jupyter

# 3. Run the notebook
jupyter notebook prompt_techniques.ipynb
```

---

## Why these tasks?

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

## Roadmap

* [ ] `02_prompt_diff.ipynb` — measure semantic shift between prompt variants
* [ ] `03_eval_harness.ipynb` — LLM-as-judge scoring
* [ ] `04_rag_basics.ipynb` — local RAG over personal documents

---

## Philosophy

Prompt engineering isn't a bag of tricks.

It's **interface design for probabilistic reasoning systems**.

---
