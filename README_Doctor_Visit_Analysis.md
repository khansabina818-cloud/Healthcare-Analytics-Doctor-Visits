# Doctor Visit Analysis

## Project Overview

**Doctor Visit Analysis** is a healthcare analytics project developed using Python, Pandas, NumPy, Matplotlib, and Seaborn. The project analyzes a dataset of **5,190 patient records** to explore doctor/hospital visits, illness levels, gender, age, income, reduced activity due to illness, health status, and health-insurance coverage.

The analysis uses descriptive statistics, grouping, correlation analysis, and visualizations to understand patterns in healthcare usage and patient characteristics.

## Project Objectives

The main objectives of this project are to:

- Analyze the number of people according to their illness level.
- Examine the gender distribution of the dataset.
- Analyze the distribution of patient income.
- Study reduced activity days due to illness by gender.
- Identify whether missing values are present in the dataset.
- Analyze correlations between numerical variables.
- Explore the relationship between income and hospital visits.
- Compare the number of male and female records.
- Analyze government health insurance coverage related to low income and old age/disability/veteran status.
- Analyze the percentage of people having private health insurance.
- Visualize the total reduced activity by gender.

## Technologies Used

- **Python**
- **Pandas** – data loading, filtering, grouping, and analysis
- **NumPy** – numerical operations
- **Matplotlib** – data visualization
- **Seaborn** – statistical visualization
- **Jupyter Notebook** – project development environment

## Dataset Information

The notebook contains **5,190 records** and **13 columns**.

### Dataset Columns

| Column | Description |
|---|---|
| `Unnamed: 0` | Record/index identifier |
| `visits` | Number of doctor/hospital visits represented in the dataset |
| `gender` | Gender of the patient |
| `age` | Age-related numerical value |
| `income` | Patient income-related numerical value |
| `illness` | Illness level/count represented as a numeric category |
| `reduced` | Number of days of reduced activity due to illness |
| `health` | Health-status-related numerical value |
| `private` | Whether the person has private health insurance (`yes`/`no`) |
| `freepoor` | Government health insurance associated with low-income status (`yes`/`no`) |
| `freerepat` | Government health insurance associated with old age, disability, or veteran status (`yes`/`no`) |
| `nchronic` | Indicator for non-chronic condition/status (`yes`/`no`) |
| `lchronic` | Indicator for long-term/chronic condition/status (`yes`/`no`) |

> **Note:** The notebook uses the dataset as provided and does not define the exact measurement units for fields such as `age`, `income`, and `health`. Therefore, this README does not assign additional units or meanings beyond what is supported by the notebook.

## Dataset Summary

According to the notebook:

- **Total records:** 5,190
- **Total columns:** 13
- **Numeric columns:** 7
- **Categorical/object columns:** 6
- **Missing values:** The notebook checks for missing values using a heatmap. The displayed dataset information shows all 5,190 records as non-null for every column.

### Gender Distribution

- Female: **2,702**
- Male: **2,488**

### Illness Distribution

| Illness Level | Number of Records |
|---:|---:|
| 0 | 1,554 |
| 1 | 1,638 |
| 2 | 946 |
| 3 | 542 |
| 4 | 274 |
| 5 | 236 |

The largest group in the notebook is illness level **1**, with 1,638 records.

## Analysis Performed

### 1. Data Loading

The dataset is loaded into a Pandas DataFrame using `pd.read_csv()`.

```python
df = pd.read_csv("Healthcare Analytics for Doctor Visits.csv")
```

The first 10 records are displayed using:

```python
df.head(10)
```

### 2. Dataset Information

The `df.info()` function is used to inspect:

- Number of records
- Number of columns
- Data types
- Non-null values
- Memory usage

The dataset contains 5,190 entries and 13 columns.

### 3. Illness Analysis

The project calculates the number of people in each illness category using:

```python
df["illness"].value_counts()
```

This helps identify how the records are distributed across different illness levels.

### 4. Gender Analysis

The number of male and female records is calculated using:

```python
df["gender"].value_counts()
```

The result shows:

- Female: 2,702
- Male: 2,488

A histogram is also used to visualize the gender distribution.

### 5. Income Distribution

A box plot is used to visualize the distribution of income:

```python
y = list(df.income)
plt.boxplot(y)
plt.show()
```

The box plot helps examine the central distribution and spread of income as well as potential outliers.

### 6. Reduced Activity Due to Illness

The project groups the data by gender and reduced-activity days:

```python
df.groupby(["gender", "reduced"]).mean(numeric_only=True)
```

This analysis helps examine how other numerical variables vary across gender and different levels of reduced activity.

A horizontal bar chart is also created to compare the total reduced activity by gender.

### 7. Missing Value Analysis

A Seaborn heatmap is used to visually inspect missing values:

```python
sns.heatmap(df.isnull(), cbar=False, cmap="viridis")
```

The dataset information displayed in the notebook shows all columns with 5,190 non-null values.

### 8. Correlation Analysis

A correlation matrix is visualized using a heatmap:

```python
sns.heatmap(
    df.corr(numeric_only=True),
    cbar=True,
    annot=True,
    cmap="Blues"
)
```

This helps identify the strength and direction of relationships between numerical variables.

### 9. Income vs. Hospital Visits

A scatter plot is used to investigate the relationship between income and visits:

```python
plt.scatter(x="income", y="visits", data=df)
```

The visualization provides a way to examine whether changes in income are associated with differences in the number of visits.

### 10. Health Insurance Analysis

The project analyzes three insurance-related indicators:

1. Government health insurance associated with low-income status (`freepoor`)
2. Government health insurance associated with old age, disability, or veteran status (`freerepat`)
3. Private health insurance (`private`)

Pie charts are used to display the `yes` and `no` proportions for each category.

## Visualizations Created

The notebook includes the following visualizations:

- Income box plot
- Missing-value heatmap
- Correlation heatmap
- Income vs. visits scatter plot
- Gender distribution histogram
- Government low-income insurance pie chart
- Government old-age/disability/veteran insurance pie chart
- Private health insurance pie chart
- Reduced activity by gender horizontal bar chart

## Key Findings Supported by the Notebook

- The dataset contains **5,190 patient records** across **13 variables**.
- Female records (2,702) are slightly higher than male records (2,488).
- Illness level **1** has the highest number of records (1,638).
- Illness level **5** has the lowest number of records (236).
- The notebook's `df.info()` output shows **no null values** across the 13 columns.
- Income distribution is examined using a box plot, allowing the spread and possible outliers to be identified visually.
- The relationship between income and visits is explored through a scatter plot.
- Correlations among numerical variables are examined using a correlation heatmap.
- Insurance coverage is analyzed separately for low-income government coverage, government coverage associated with old age/disability/veteran status, and private insurance.

## Project Workflow

```text
Import Libraries
       ↓
Load Healthcare Dataset
       ↓
Inspect Dataset
       ↓
Check Data Types & Missing Values
       ↓
Analyze Illness & Gender
       ↓
Analyze Income Distribution
       ↓
Analyze Reduced Activity
       ↓
Analyze Correlations
       ↓
Analyze Income vs. Visits
       ↓
Analyze Health Insurance
       ↓
Create Visualizations
       ↓
Interpret Results
```

## How to Run the Project

### Prerequisites

Install Python and the required libraries:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Run the Notebook

1. Download or clone this project.
2. Place the healthcare dataset in an accessible location.
3. Open the notebook:

```bash
jupyter notebook
```

4. Open `Sabina_DOCTOR_VISIT_ANALYSIS(1).ipynb`.
5. Update the CSV file path in the `pd.read_csv()` cell if required.
6. Run the cells from top to bottom.

### Important

The original notebook contains a local Windows file path:

```python
C:\Users\khans\Downloads\1776250375-P2-Healthcare Analytics for Doctor Visits.csv
```

This path will only work on the original computer/environment. When sharing the project, replace it with a relative path such as:

```python
df = pd.read_csv("data/Healthcare Analytics for Doctor Visits.csv")
```

## Project Structure

A recommended project structure is:

```text
Doctor-Visit-Analysis/
│
├── README.md
├── Sabina_DOCTOR_VISIT_ANALYSIS(1).ipynb
│
└── data/
    └── Healthcare Analytics for Doctor Visits.csv
```

## Skills Demonstrated

This project demonstrates practical beginner-to-intermediate data analytics skills:

- Python programming
- Pandas DataFrame handling
- Data inspection
- Frequency analysis
- GroupBy analysis
- Descriptive analysis
- Missing-value checking
- Correlation analysis
- Data visualization
- Matplotlib
- Seaborn
- Healthcare data analysis
- Interpreting analytical charts

## Future Scope

The project can be extended by:

- Cleaning and standardizing column names.
- Creating clearer categorical labels for numeric variables.
- Performing deeper statistical analysis.
- Building an interactive dashboard using Power BI or Tableau.
- Adding filters for gender, illness level, insurance type, and age.
- Performing more detailed analysis of hospital visits.
- Exploring chronic-condition indicators in greater detail.
- Creating additional KPIs and summary dashboards.
- Using statistical or machine-learning methods to investigate factors associated with healthcare visits.

## Conclusion

The Doctor Visit Analysis project provides a structured exploration of healthcare-related patient data using Python. It examines illness, gender, income, reduced activity, hospital visits, correlations, and insurance coverage through numerical analysis and visualizations.

The project demonstrates how Python-based data analysis can be used to transform a healthcare dataset into understandable patterns and visual insights.
