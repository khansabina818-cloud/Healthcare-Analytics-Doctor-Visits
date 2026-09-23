# Healthcare Analytics – Doctor Visits Analysis

## Project Overview

This project analyzes doctor visit data to understand healthcare utilization patterns based on demographics, income, illness, health conditions, insurance, and chronic diseases.

## Dataset

The project uses a CSV dataset containing **5,190 healthcare records** and 13 columns.

Main variables include:

- `visits` – Number of doctor visits
- `gender` – Patient gender
- `age` – Age category/code
- `income` – Income level/code
- `illness` – Illness category
- `reduced` – Number of days activity was reduced due to illness
- `health` – Health condition/health score
- `private` – Private health insurance status
- `freepoor` – Free healthcare coverage for low-income individuals
- `freerepat` – Free/repatriation healthcare coverage
- `nchronic` – Chronic condition status
- `lchronic` – Another chronic condition status

## Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

## Analysis Performed

1. Dataset loading and inspection
2. Row and column count
3. Data type checking
4. Missing-value checking
5. Duplicate-row checking
6. Descriptive statistics
7. Unique-value analysis
8. Doctor visit distribution
9. Average doctor visits
10. Patients with and without doctor visits
11. Gender-wise analysis
12. Age-category analysis
13. Income-category analysis
14. Illness analysis
15. Health-category analysis
16. Reduced-activity analysis
17. Private insurance analysis
18. Free healthcare coverage analysis
19. Chronic-condition analysis
20. Correlation analysis
21. KPI summary and key observations

## Key KPIs

The notebook calculates:

- Total Records
- Total Doctor Visits
- Average Doctor Visits
- Patients with at least one Doctor Visit

## Key Observations

- The dataset contains 5,190 healthcare records.
- Doctor visits are concentrated heavily around zero visits.
- The average number of doctor visits per record is approximately 0.30.
- Gender-wise visit patterns can be compared using average visits.
- Illness categories show differences in average doctor-visit frequency.
- Health categories can be compared to understand healthcare utilization patterns.
- Chronic-condition status can be examined for differences in doctor visits.
- Income and insurance-related categories provide additional dimensions for healthcare utilization analysis.

## Important Note

The analysis identifies patterns and associations in the dataset. Correlation or group-level differences should not be interpreted as proof of causation.

## How to Run

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Open the notebook

Open:

`SABINA_DOCTOR_VISITS_ANALYSIS(1).ipynb`

in Jupyter Notebook or JupyterLab.

### 3. Keep the dataset accessible

Place the CSV dataset in the same working folder as the notebook, or update the CSV path in the notebook.

## Project Files

- `SABINA_DOCTOR_VISITS_ANALYSIS(1).ipynb` – Analysis notebook
- `1776250375-P2-Healthcare Analytics for Doctor Visits(2).csv` – Dataset
- `requirements.txt` – Python dependencies
- `README.md` – Project documentation
