# Walmart Sales Analysis

An exploratory data analysis (EDA) of Walmart weekly sales across 45 stores. I cleaned the data, checked the outliers, and looked for what actually drives sales: season, store, holidays, and economic factors like unemployment and fuel price.

**Full report (PDF):** [reports/walmart_sales_analysis_final_report.pdf](reports/walmart_sales_analysis_final_report.pdf)

## About the data

- **Rows:** 6,435 weekly records
- **Stores:** 45
- **Period:** February 2010 to October 2012
- **Columns:** `store`, `date`, `weekly_sales`, `holiday_flag`, `temperature`, `fuel_price`, `cpi`, `unemployment`

## What I did

1. **Cleaned the data.** I checked for missing values, duplicates and impossible values (there were none). I changed the column names to lowercase and converted `date` to a real date type.
2. **Checked outliers** with the IQR method. I found 34 very high sales weeks, 3 very cold temperature readings and 481 unemployment values. I kept them all because they are real values (holiday spikes and a few stores in high-unemployment areas).
3. **Explored the data** with histograms, a correlation heatmap, box plots, a line chart over time, a scatter plot and a store-by-store comparison.
4. **Wrote down the insights and recommendations** from what the charts showed.

## Key findings

- **Sales are strongly seasonal.** Average weekly sales stay around 1.0M most of the year, spike around Thanksgiving and peak just before Christmas (about 1.8M).
- **The holiday flag misses the biggest week.** The pre-Christmas week is not flagged as a holiday in this data, so most of the highest sales fall in non-holiday weeks.
- **The store matters more than any economic factor.** Store 20 averages about 2.1M a week, while store 33 averages about 260K, roughly 8 times less. Temperature, fuel price and CPI are almost unrelated to sales.
- **Higher unemployment goes with lower sales.** Stores in high-unemployment areas (12, 28, 38) averaged about 906K a week, compared with about 1.48M in low-unemployment areas (4, 23, 40), roughly 39% lower. This only compares 3 stores per group and store size may also play a part, so it shows a link, not proof of cause.

## Recommendations

- Plan inventory and staffing ahead of late November and late December every year.
- Study what the top stores (like 20 and 4) do differently and try it in weaker stores.
- Try targeted promotions and lower-priced products in high-unemployment areas.

## Tools used

Python, pandas, matplotlib, seaborn, Jupyter Notebook

## Project structure

```
walmart-sales-analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── walmart.csv
│   └── walmart_cleaned.csv
├── notebooks/
│   └── walmart_sales_analysis.ipynb
└── reports/
    └── walmart_sales_analysis_final_report.pdf
```

## How to run it

1. Download or clone this repo.
2. Install the libraries:
   ```
   pip install -r requirements.txt
   ```
3. Open `notebooks/walmart_sales_analysis.ipynb` in Jupyter or VS Code and run the cells from top to bottom.