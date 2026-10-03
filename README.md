# Black Friday Purchase Analysis

Exploratory data analysis and inferential statistics on a retail purchase dataset, examining how purchase amount relates to customer age and gender.

## Dataset

The Black Friday / Walmart purchase dataset — ~263,000 transactions with customer demographics (gender, age, occupation, city category) and purchase amounts.

- Source: [Black Friday Dataset on Kaggle](https://www.kaggle.com/datasets/sdolezel/black-friday)
- Not included in this repo (large file) — download it and place it in this folder as `purchase_case_study_inferential_statistics.csv`, or update the path in the notebook's load cell.

## What this analysis does

1. **Data cleaning** — standardized the `Stay_In_Current_City_Years` column (handled the non-numeric `'4+'` label), filled expected missing values in `Product_Category_2`/`Product_Category_3`, and dropped remaining incomplete rows.
2. **Outlier handling** — detected and removed outliers in `Purchase` using the IQR method.
3. **Encoding** — converted categorical fields (`Gender`, `Age`, `City_Category`, `Product_ID`) to numeric labels.
4. **Hypothesis testing:**
   - **One-sample t-test:** is the average purchase amount for men aged 18–25 equal to ₹10,000?
   - **Two-sample t-test:** do men and women aged 18–25 spend the same amount on average?

## Key findings

- The average purchase amount for men aged 18–25 is **not** ₹10,000 — it's significantly lower (≈ ₹9,493 in the sampled data), p ≈ 1.78e-09.
- Men and women aged 18–25 do **not** spend the same amount on average — men spent more (≈ ₹9,392) than women (≈ ₹8,380), p ≈ 1.49e-84.
- Both results are statistically significant well beyond the standard α = 0.05 threshold.

## Tools used

Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy (`ttest_1samp`, `ttest_ind`), scikit-learn (`LabelEncoder`)

## Files

- `black_friday_purchase_analysis.ipynb` — the full analysis, cleaned and documented end-to-end
- `requirements.txt` — Python packages needed to run it

## Running it yourself

```bash
pip install -r requirements.txt
jupyter notebook black_friday_purchase_analysis.ipynb
```
