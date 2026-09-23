# AI Fluency Training — Day 2

## Overview

Day 2 focuses on understanding and comparing different approaches for solving problems with Large Language Models (LLMs).

The main approaches explored are:

- Direct Prompting
- Chain-of-Thought (CoT)
- ReAct (Reasoning + Acting)
- Self-Consistency

The experiments use Python and an LLM API to observe how different prompting and agent approaches behave on reasoning and tool-dependent questions.

---

## Objectives

- Understand Direct Prompting and its limitations.
- Understand Chain-of-Thought reasoning.
- Understand the ReAct agent approach.
- Compare Direct Prompting, CoT, and ReAct.
- Use Self-Consistency to run the same reasoning question multiple times.
- Observe whether repeated runs produce consistent answers.
- Analyze the strengths and limitations of each approach.

---

## Project Structure

```text
Day2/
│
├── Output/
│   └── Screenshots
│
├── analysis.md
├── cot_compare.py
├── react_trace.py
├── requirements.txt
└── self_consistency.py
