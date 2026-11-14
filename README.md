# Global Cancer Patients Analysis

An object-oriented Python pipeline that loads, cleans, analyses and visualises 50,000 cancer patient records (2015–2024), built with Pandas, NumPy and Matplotlib.

**Dataset:** [Global Cancer Patients 2015–2024](https://www.kaggle.com/datasets/zahidmughal2343/global-cancer-patients-2015-2024) (Kaggle)
**Author:** Ani Hovhannisyan

## What's inside

The whole project is one notebook, `cancer_analysis.ipynb`, built around three classes:

| Class | Responsibility |
|-------|----------------|
| `DataLoader` | Reads the CSV, drops duplicates, fills missing values (median for numbers, mode for text), fixes types, standardises text |
| `DataAnalyzer` | Descriptive stats, survival by cancer type / stage / age group / year, cases per year, top countries, gender split, cost vs survival, risk-factor correlations |
| `Visualizer` | Produces 8 annotated plots |

The pipeline runs in three steps: **load and clean**, then **analyse**, then **visualise**.

## The data

50,000 patients from 10 countries, 15 columns: demographics (age, gender, country, year), five risk factors (genetic risk, air pollution, alcohol use, smoking, obesity level), cancer type and stage, treatment cost (USD), survival years and a severity score.

## Plots

1. Age distribution
2. Mean survival by cancer type
3. Mean survival by cancer stage
4. Cases per year
5. Top 10 countries by number of cases
6. Treatment cost vs survival (density heatmap)
7. Gender distribution
8. Genetic risk vs severity score (with trend line)

## Key findings

- **Genetic risk is the strongest predictor of severity** (r ≈ 0.48), well above the lifestyle and environmental factors.
- **Cancer stage drives survival**: earlier stages do better, Stage IV is lowest.
- **Treatment cost is unrelated to survival** (Pearson r close to 0).
- **Cancer type has only a small effect** on survival (about 4.98 to 5.03 years on average).
- Cases, countries and genders are almost evenly distributed, so the dataset is well balanced. That also means the results should be read as an exercise in method, not as clinical evidence.

## Run it

1. Download `global_cancer_patients_2015_2024.csv` from the Kaggle link above and place it next to the notebook. The CSV is not stored in this repo.
2. Install the dependencies and start Jupyter:

```bash
pip install pandas numpy matplotlib jupyter
jupyter notebook cancer_analysis.ipynb
```

3. Run all cells from top to bottom.
