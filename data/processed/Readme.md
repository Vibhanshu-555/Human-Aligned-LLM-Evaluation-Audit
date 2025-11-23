# 📂 Processed Data

This folder contains **cleaned, standardized, and analysis-ready datasets** derived from the original [MT-Bench](https://huggingface.co/datasets/lmsys/mt_bench_human_judgments) evaluation files located in [`data/raw/`](../raw).

These files are used directly for:
- Bias and agreement analysis
- Category-wise model performance comparisons
- Visualization and Power BI dashboard reporting

---

## 🧹 Transformations Applied
The following steps were completed before export:

✔ Column names standardized  
✔ `question_id` converted to string for merging  
✔ Winner labels normalized into:
- `winner_model` → the actual winning model 
- `is_tie` → boolean flag  
✔ Task category merged from metadata  
✔ Derived metrics added where needed  

---

## 📑 Files Included
| File Name | Description |
|----------|-------------|
| `human_model_rankings_for_powerbi.csv` | Human-validated win-rate rankings for each model × category |
| `agreement_rates_for_powerbi.csv` | Agreement & disagreement percentages per task type |
| `sota_integration_verified_for_powerbi.csv` | Final validated recommendations with 2025 SOTA alignment |
| `human_gpt_comparison.csv` | Row-level match of human vs GPT-4 decisions |
| `disagreement_examples.csv` | Specific cases where judgments do not match |

> These are the core files powering the analytical dashboard.

---

## 🔒 Handling Notes
📌 **Do not modify manually** — regenerate from the notebook if changes are needed  
📌 Serves as the **single source of truth** for downstream visualization tools  

---

### Purpose
To ensure:
- Reproducibility  
- Clear data lineage  
- Error-free dashboard integration  
---

