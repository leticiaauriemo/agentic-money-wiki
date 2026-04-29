---
title: "Summary: Lost in the Middle (Liu et al., 2023)"
type: summary
topic: personal-project
source_type: academic
tags: [memory-wall, context-window, attention, long-context, instruction-dilution, primacy-bias, recency-bias]
sources: [lost-in-the-middle-liu-2023.pdf]
created: 2026-04-22
updated: 2026-04-22
---

# Summary: Lost in the Middle (Liu et al., 2023)

**Authors:** Nelson F. Liu, Kevin Lin, John Hewitt, Ashwin Paranjape, Michele Bevilacqua, Fabio Petroni, Percy Liang (Stanford University, UC Berkeley, Samaya AI)

**Source:** `lost-in-the-middle-liu-2023.pdf` | arXiv:2307.03172

**Answers:** *What is the empirical basis for the instruction-dilution failure mode of the memory wall?*

---

## Core finding

Language models do not robustly use information in long input contexts. Specifically:

**The U-shaped performance curve:** Model performance is highest when relevant information appears at the **beginning** (primacy bias) or **end** (recency bias) of the input context, and degrades significantly when relevant information is buried in the **middle** — even for models explicitly designed for long contexts.

> **Key quote:** "Performance is often highest when relevant information occurs at the beginning or end of the input context, and significantly degrades when models must access relevant information in the middle of long contexts, even for explicitly long-context models." (Abstract)

---

## Experiments and results

**Multi-document question answering:** Models given a set of documents (some relevant, some not) and asked to answer a question. The position of the relevant document was varied systematically.

Key result: When relevant information is placed in the **middle** of the input context, GPT-3.5-Turbo's performance drops below its **closed-book performance** (56.1%) — meaning the model does better ignoring all documents than trying to use them when the relevant one is buried in the middle.

**Key-value retrieval (synthetic task):** Models given JSON key-value pairs and asked to retrieve a specific value. Even on this minimal synthetic task, models struggle when the relevant key-value pair appears in the middle of a long context.

**Extended-context models:** Extended-context models (designed specifically for long contexts) show nearly identical U-shaped curves as standard models — the advertised larger context window does not solve the attention degradation problem.

**Open-domain QA (external validity):** When retrieving from Wikipedia for NaturalQuestions-Open, model performance saturates long before retriever recall saturates. Using 50 documents instead of 20 only improves performance ~1.5% (GPT-3.5-Turbo) and ~1% (Claude-1.3) — marginal improvement from providing more information.

---

## Why this happens

The paper tests three hypotheses:

**Model architecture.** Encoder-decoder models are more robust to position changes *within* their training sequence length, but show U-shaped curves on sequences longer than training. Decoder-only models consistently show U-shaped patterns.

**Query-aware contextualization.** Placing the query both before and after the documents enables near-perfect performance on the synthetic key-value task, but minimally affects multi-document QA trends.

**Instruction fine-tuning.** Even base models (without instruction fine-tuning) show the U-shaped curve — the pattern is not an artifact of instruction tuning.

---

## The practical implication for agents

In long-running agent workflows:
- Original task instructions are placed at the beginning of context
- Accumulated tool outputs, intermediate results, and error messages fill the middle
- The agent's original instructions effectively get "lost in the middle" as the job progresses
- The agent continues to execute but toward a drifted or degraded goal

This is the empirical foundation for **Failure Mode 2: Instruction Dilution** in [[memory-wall]].

**Bigger context windows don't fix this.** The paper explicitly shows that extended-context models perform identically to standard models on the U-shaped curve — longer context windows push out the hard overflow limit but don't improve per-position attention quality.

---

## Key quotes

> "When relevant information is placed in the middle of its input context, GPT-3.5-Turbo's performance on the multi-document question task is lower than its performance when predicting without any documents (i.e., the closed-book setting; 56.1%)." (Section 2.3)

> "Extended-context models are not necessarily better at using their input context." (Section 2.3)

> "Model performance saturates long before retriever recall saturates, indicating that current models fail to effectively use additional retrieved documents." (Section 5)

---

## Relevance to thesis

1. **Empirical backbone for the memory wall argument.** When presenting the startup thesis, this paper provides peer-reviewed Stanford evidence that the instruction-dilution failure mode is real, measurable, and not solved by larger context windows.

2. **Why decomposition is necessary.** If models can't reliably attend to information in the middle of long contexts, then the only robust architectural response is to keep each agent's context short — which requires decomposition across multiple focused specialists.

3. **Why external memory matters.** Task-relevant information must be stored externally and retrieved at the point of need, not accumulated in context — because once it's in the middle, models can't reliably use it.

---

## Related pages

[[memory-wall]]
[[subagents-and-orchestration]]
[[the-five-problems]]

## Source

- [[lost-in-the-middle-liu-2023]] (Liu, Lin, Hewitt, Paranjape, Bevilacqua, Petroni, Liang — Stanford/Berkeley/Samaya AI, 2023)
