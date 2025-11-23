# 📘 Methodology

## 🎯 Project Objective
This project evaluates the **credibility of AI-based evaluation systems** by comparing GPT-4 judgments against **real human preferences** across MT-Bench task categories. The goal is to quantify evaluator bias, reveal where AI judges fail, and establish a **human-validated baseline** that supports reliable model ranking and recommendation.

---

## 📂 Datasets Used

This analysis uses **three MT-Bench evaluation datasets**:

### **1️⃣ [`human.csv`](../data/raw/human.csv) — Ground-Truth Human Votes**
Contains human evaluator outcomes for pairwise LLM comparisons:
- `model_a`, `model_b`
- `winner` (A / B / tie)
- conversation responses

Used to determine **true model strength**.

---

### **2️⃣ [`gpt4_pair.csv`](../data/raw/gpt4_pair.csv) — GPT-4 as Judge**
Same structure as human data but judged by GPT-4.
Used to measure:
- **AI–Human alignment**
- **Evaluation bias** in model selection  

---

### **3️⃣ [`question.jsonl`](../data/raw/question.jsonl) — Task Metadata**
Includes category labels for every evaluated prompt:
- `question_id`
- `category` *(e.g., math, coding, writing, reasoning, roleplay, extraction)*

Used to **segment performance by task type**.

---

## 🧠 Analytical Workflow

### **1. Data Standardization**
- Harmonized column names
- Converted `question_id` to string for proper merging
- Verified schema and missing values

---

### **2. Normalization of Winner Labels**
Standardized all label variations into consistent forms:
- `winner_model` → actual model selected
- `is_tie` → boolean flag for ties

This enables correct metric computations.

---

### **3. Category Mapping**
Merged judgment datasets with question metadata to provide:
> 🧩 **Model performance within each task category**

---

### **4. Metric Calculations**
For each model × category pair:

| Metric | Purpose |
|--------|---------|
| **Appearances** | Occurrences of model in comparisons |
| **Wins** | Number of times model won |
| **Tie Count** | Ties it was part of |
| **Effective Wins** | `wins + 0.5 × ties` |
| **Win Rate** | `effective_wins / appearances` |
| **Agreement Rate** | Human = GPT-4 |
| **Bias Gap** | GPT-4 win rate − Human win rate |

---

### **5. Bias & Alignment Analysis**
- Measured **overall disagreement** rate
- Identified **high-risk categories** (Reasoning & Math)
- Detected **self-preference bias** toward GPT-4
- Compared **expert vs author disagreement levels**

---

## 📊 Final Deliverable

A **three-page evaluation audit [dashboard](../dashboard/Human_Aligned_LLM_Evaluation_Audit.pbix)** designed for decision-makers:

| Page | Focus | Key Question Answered |
|------|-------|---------------------|
| 1️⃣ [**AI Judge Bias**](../dashboard/Page_1_The_Crisis.png) | Misalignment & bias mapping | *Where and why does AI judgment fail?* |
| 2️⃣ [**Human-Validated Baseline**](../dashboard/Page_2_The_Solution.png) | True performance rankings by task | *What do humans prefer and trust?* |
| 3️⃣ [**Human + SOTA Recommendations**](../dashboard/Page_3_The_Conclusion.png) | Actions based on updated market reality | *Which model is best for each task now?* |

This structure forms a complete narrative:
> **Problem → Solution → Conclusion**

---

## ✔ Outcome
This project **exposes systemic biases** in AI-judge evaluation and delivers a **reliable, human-backed foundation** for model comparison and deployment decisions.

> 🔍 **Conclusion:** Automated evaluation alone is not enough. Human judgment remains critical for trustworthy AI benchmarking.
