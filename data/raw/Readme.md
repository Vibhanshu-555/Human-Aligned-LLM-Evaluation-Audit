# 📂 Raw Data

This folder contains the **original, unmodified datasets** used for the LLM Evaluation Audit.

These files come directly from the [MT-Bench](https://huggingface.co/datasets/lmsys/mt_bench_human_judgments) evaluation pipeline and are used to analyze the credibility of GPT-4 as an evaluator compared to human judgment.

## 📑 Files Included
- **human.csv** — Human-annotated pairwise model comparisons  
- **gpt4_pair.csv** — GPT-4–judged pairwise model comparisons  
- **question.jsonl** — Metadata including task category for each evaluation

## 🔒 Handling Notes
- **Do not edit** these files directly  
- Only project scripts should reference this folder  
- Any cleaning or preprocessing should be done in the [`data/processed/`](../processed) folder  

## 🧠 Purpose
These raw files serve as the foundation for:
- Bias detection  
- Agreement/disagreement analysis  
- Human-validated model performance metrics  

> 📌 This folder ensures that the project remains **reproducible** and that the original dataset is always preserved.
