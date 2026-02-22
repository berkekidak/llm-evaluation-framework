# llm-evaluation-framework

A lightweight framework for **repeatable, comparable LLM evaluations**.
Run tasks against one or more models, score outputs with automatic metrics and LLM-as-judge rubrics, and generate reports you can track over time.

## Why this exists
Evaluating LLMs is often messy:
- prompts change
- datasets are inconsistent
- scoring is not reproducible
- results live in notebooks and get lost

This repo aims to make evaluations:
- **versioned** (configs, prompts, datasets, model params)
- **repeatable** (same run produces the same artifacts)
- **comparable** (standard outputs, metrics, and reports)
- **auditable** (store raw generations + scoring explanations)

## What it supports (planned)
- Task suites: QA, summarization, extraction, classification, tool use
- Metrics: exact match, F1, ROUGE, BLEU, BERTScore (optional), custom metrics
- LLM-as-judge: rubric scoring with calibration prompts and judge agreement checks
- Pairwise comparisons: A/B preference tests
- Reporting: JSONL logs + aggregated tables + simple HTML/Markdown reports

## Quick start (once code exists)
```bash
# 1) create venv
python -m venv .venv
source .venv/bin/activate

# 2) install
pip install -e .

# 3) run an eval
python -m llmeval run configs/example.yaml
