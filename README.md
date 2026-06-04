# Employee Attrition Risk Analysis
**People Analytics Portfolio Project**  
Om S Omanwar | MBA HRD Candidate | Delhi School of Economics (2026-28)

---

## Overview

This project applies machine learning to the IBM HR Analytics dataset (1,470 employees) to identify employees at elevated attrition risk and translate those findings into a business-ready intervention strategy.

The model is not the deliverable. The business brief is.

---

## Key Results

| Metric | Value |
|--------|-------|
| Dataset | IBM HR Analytics (1,470 employees, 35 features) |
| Attrition Rate | 16.1% (above 10-12% industry benchmark) |
| Model | RandomForest with class_weight=balanced |
| Accuracy | 84% |
| Attrition Recall (baseline) | 8% |
| Attrition Recall (threshold-tuned, 0.15) | 67% |
| High-Risk Cohort | ~340 employees (23% of workforce) |
| Estimated Replacement Cost | Rs 4.2Cr |
| Intervention Cost (3 levers) | Rs 43L |
| Implied ROI | 5-9x |

---

## Top Attrition Drivers

1. **Monthly Income** -- Employees below Rs 5,000/month show 3.2x attrition risk
2. **Overtime = Yes** -- Overtime employees show 2.8x attrition risk
3. **Age under 35** -- Highest churn in early-career cohort
4. **Job Level 1-2** -- Entry/junior levels overrepresented in attrition
5. **Stock Options = 0** -- No equity participation correlates with higher exits

---

## High-Risk Cohort Profile

Employees matching ALL of the following criteria:
- Age under 35
- Job Level 1-2
- Monthly income below Rs 5,000
- Overtime = Yes
- Tenure under 3 years
- Stock options = Level 0

This cohort has an average model-predicted attrition probability of 0.61, versus a population mean of 0.18.

---

## Intervention Recommendations

| Lever | Cost | Employees Retained | Net Saving |
|-------|------|--------------------|------------|
| Compensation review (Job Level 1-2) | Rs 20L | ~45 | Rs 1.8Cr |
| Overtime audit + workload redistribution | Rs 8L | ~30 | Rs 1.2Cr |
| Stock option expansion (Job Level 1-2) | Rs 15L | ~35 | Rs 1.4Cr |
| **TOTAL** | **Rs 43L** | **~110** | **Rs 4.4Cr** |

---

## Technical Notes: Class Imbalance

This dataset has a 16% positive class (attrition = Yes). Default classifiers exploit this by predicting "Stay" almost always -- achieving ~84% accuracy but near-zero recall on the class that actually matters for intervention.

Two approaches were tested and compared:
- `class_weight='balanced'`: adjusts sample weights to give the minority class proportional influence
- Threshold tuning (0.5 to 0.15): trades precision for recall, surfacing more true attrition cases

For HR intervention purposes, this is the correct trade-off. Missing a flight risk is more expensive than an unnecessary conversation.

---

## Files

| File | Description |
|------|-------------|
| `Attrition_Analysis.ipynb` | Annotated Jupyter notebook: EDA, preprocessing, model, feature importance, cohort profile |
| `Attrition_Business_Brief.docx` | Executive business brief with findings, cohort profile, intervention levers, ROI table |
| `Attrition_Analysis_Deck.pptx` | 5-slide presentation deck (dark navy theme) |

---

## Dataset

IBM HR Analytics Employee Attrition dataset, available on Kaggle:  
https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset

---

## Dependencies

```
pandas
numpy
matplotlib
seaborn
scikit-learn
```

Install: `pip install pandas numpy matplotlib seaborn scikit-learn`

---

*Built during the bridge phase before MBA HRD at Delhi School of Economics (August 2026)*
