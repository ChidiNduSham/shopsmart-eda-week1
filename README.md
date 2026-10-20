# Week 1 — Mission DS01: ShopSmart Retail EDA

Exploratory Data Analysis of ShopSmart Retail Ltd.'s 2025 sales data (nine linked tables, 50,000 orders), written in Python with pandas, matplotlib and seaborn.
The notebook, report and presentation all use the same numbers: **revenue means Completed orders** unless a figure says "all orders".

## Folder structure
```
Week1_DataScience_Project/
├── Week1_EDA.ipynb          the full analysis (Parts 1–8 of the brief), run from top to bottom
├── Cleaned_Data/            cleaned tables, feature tables, Cleaning_Log.csv, kpi_table.csv
├── Visualizations/          all charts (01–10 are the ten required; 11–16 support the analysis)
├── EDA_Report.pdf           17-page report
├── Presentation.pptx        15-slide summary deck
├── requirements.txt         Python packages
├── README.md                this file
└──  Raw_Data/                the supplied CSV files (unchanged)
```

## How to run
```bash
python -m venv .venv && source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook Shammah_Ndubuisi_Week1 Submission.ipynb                          # Kernel → Restart & Run All
```
Open the notebook from this folder: it reads `Raw_Data/` and writes `Cleaned_Data/` and `Visualizations/`.

## What the notebook covers
| Part | Content |
|---|---|
| 1 | Environment setup |
| 2 | Load all nine tables; head, tail, shape, columns, data types, missing values |
| 3 | Cleaning: duplicates, missing values, data types, dates, renaming, inconsistent values — each step logged |
| 4 | Merged analysis tables and the ten required KPIs |
| 5 | The ten required charts |
| 6 | Correlation matrix, heatmap, pair plot and explanations |
| 7 | Feature engineering: profit margin, order month and quarter, age group, customer lifetime value, discount percentage, days since last purchase, inventory status |
| 8 | Ten business questions, each with a table or chart and a written answer |

## Headline results
* Revenue from Completed orders is **₦2.50bn**; only **33.0%** of booked order value (₦7.58bn) is Completed, 33.7% is Cancelled and 33.3% is Pending.
* Average order value ₦151,057; return rate 4.88% (all orders); inventory value at cost ₦3.17bn.
* Stores, regions, customer segments, categories and months perform alike; the best store changes depending on whether all orders or only Completed orders are counted.
* Data problems: 24.3% of orders sold below cost; half of the returns are dated before the order; two-thirds of returns relate to orders never completed; the discount is subtracted as a flat amount.
* Inventory: 23 products need restocking, while 307 products hold more than a year of stock (₦2.72bn).

## Assumptions
* Currency is Nigerian naira (₦), inferred from the store locations; the data does not state it.
* Revenue = `line_total` on Completed orders (booked value for all orders is shown for comparison).
* `Discount` is kept as recorded (a flat amount); whether it is a percentage is a question for the client.
* Days since last purchase is measured from 1 January 2026, the day after the last order.
* Customer lifetime value = profit in the year × an assumed 3-year lifespan.

