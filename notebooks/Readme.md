# 📓 Notebooks

This folder contains the **Jupyter Notebook(s)** used to perform the full analytical workflow for the LLM Evaluation Audit.

The notebook includes:
- Data loading and inspection  
- Preprocessing and normalization  
- Merging metadata with evaluation results  
- Win-rate and bias metric computation  
- Human vs GPT-4 agreement analysis  
- Exporting processed datasets for dashboard use  

---

## 📑 Files Included

| File | Purpose |
|------|---------|
| `analysis.ipynb` | Full data processing pipeline and analysis results |
| `analysis.html` | Static, view-only version for GitHub preview |

> The HTML version allows reviewers to explore the notebook **without requiring a Python environment**.

---

## 🛠 Environment Notes

The notebook requires:
- Python 3.10+
- Pandas, NumPy
- Matplotlib/Seaborn (optional for visual validation)
- Jupyter or VS Code support

---

## 🧠 Purpose

This notebook ensures full **transparency and reproducibility** of all transformations done to the MT-Bench datasets.

All data exported from this workflow powers:
- 📊 Visual analytics
- 📈 Power BI Dashboard reporting
- 🧪 Evaluation bias conclusions  

---

📌 *If modifications are required, update and re-export data into* `data/processed/` *instead of editing processed files directly.*
