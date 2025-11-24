# Human-Aligned LLM Evaluation Audit

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)](https://numpy.org/)
[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=power-bi&logoColor=black)](https://powerbi.microsoft.com/)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=Jupyter&logoColor=white)](https://jupyter.org/)
[![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=flat&logo=visual-studio-code&logoColor=white)](https://code.visualstudio.com/)

## Executive Summary
This project evaluates how well GPT-4 judgments align with human preferences in **8 task categories** across **3,500+ model comparisons** involving **6 prominent LLMs** from the MT-Bench dataset. GPT-4 matches human judgment only **53%** of the time, with significantly lower alignment in **Reasoning** and **Math** tasks. A human-validated baseline is developed and visualized in a Power BI dashboard to help ensure evaluation methods support real user expectations.

**Dashboard & Files:**  
- [Power BI Dashboard (.pbix)](./dashboard/Human_Aligned_LLM_Evaluation_Audit.pbix)  
- [Dashboard PDF](./dashboard/Human_Aligned_LLM_Evaluation_Audit.pdf)
- [Analysis Notebook](./notebooks/LLM_Evaluation_Audit.ipynb)

All files included in this repository.

## Problem Context
Most modern LLM benchmarks rely on **AI judges scoring other AI systems**. This is efficient, but introduces risks:

- Performance claims may not represent human expectations
- Critical decision tasks may be over- or under-valued

Organizations rely on these scores for **model selection, deployment decisions, and product outcomes**. Understanding evaluator reliability is essential for informed decisions.

---

## Methodology
- **Data Exploration (EDA):** Inspected schema, distribution, and label quality across human and GPT-4 judgment files  
- **Data Cleaning:** Standardized winner formats, fixed data type mismatches, resolved identifier inconsistencies  
- **Metadata Enrichment:** Attached category labels from `question.jsonl` to all comparisons  
- **Metric Engineering:**  
  - Win rate, appearances, tie-adjusted outcomes  
  - **Disagreement metrics** at category level  
  - Model performance matrix used for ranking  
- **Dashboard Reporting:** Built a three-page Power BI report explaining alignment patterns and task-specific strengths  

📌 Full workflow available in:  
[`docs/Methodology.md`](./docs/Methodology.md)

---

## Skills & Tools
- **Python (pandas):** Data wrangling, model comparison metrics  
- **Power BI:** Visual analytics, category segmentation, stakeholder reporting  
- **Analytical Skills:** Reliability analysis, evaluator disagreement measurement  
- **Data Communication:** Clear presentation of risk and insight for decisions  

---

## Results & Practical Insights

### Key Metrics
- **3,500+** human vs GPT-4 comparison rows analyzed
- **53%** overall human–GPT alignment
- Highest disagreement in:
  - **Reasoning:** 69%
  - **Math:** 64%    
- Highest agreement in Extraction and STEM tasks (~70%)  
- **79% disagreement among expert-level annotations** → More divergence under complexity  
- GPT-4 shows **systematic win-rate inflation**, shifting leaderboard positions

These insights show that disagreement is **not random**, it is task-driven and increases as complexity increases.

<p>
  <img src = './assets/Page_1_The_Crisis.png'>
</p>

---

## Recommendations
Automated LLM evaluation remains useful for low-ambiguity tasks. However, **human-validated checkpoints** are necessary before trusting benchmark scores for reasoning, math, and code-quality decisions. Aligning evaluation methods with real user expectations reduces deployment risk and supports decision confidence.

---

## Next Steps / Future Improvements
- Add **multiple evaluator models** (Claude, Gemini) to compare judge reliability  
- Incorporate **confidence scoring** to formalize evaluator trust  
- Calibrate automated scoring using **weighted human annotation**  
- Track alignment **over time** across newer LLM releases
