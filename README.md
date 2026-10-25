# Sales Data Analysis

A pandas script that analyses 100 sales transactions from January to April 2024. It checks data quality, calculates revenue metrics, and writes a Markdown report.

## Project Structure


sales-data-analysis/
├── sales_analysis.py      # Main analysis script
├── sales_data.csv         # Input data (100 rows, 7 columns)
├── analysis_report.md     # Generated report
├── requirements.txt       # Python dependency
├── README.md              # This file
└── screenshots/           # Output from each stage
    ├── 01_data_check.png
    ├── 02_metrics.png
    └── 03_report.png


## Setup

1. Clone or download this repository.
2. Install the dependency:
   
   pip install -r requirements.txt
   
3. Run the analysis from the project folder:
   
   python sales_analysis.py
   

The script must run in the same folder as sales_data.csv. It writes analysis_report.md to that folder.

## Data

sales_data.csv contains the following columns:

| Column | Description |
|---|---|
| Date | Sale date (2024-01-01 to 2024-04-09) |
| Product | Laptop, Tablet, Phone, Headphones, or Monitor |
| Quantity | Units sold in the transaction |
| Price | Unit price |
| Customer_ID | Unique customer identifier |
| Region | North, South, East, or West |
| Total_Sales | Quantity × Price |

## What the Script Does

1. *Loads the data* with pandas.read_csv and prints its shape and column names.
2. *Checks for missing values and duplicates.* Both checks found none.
3. *Cleans the data.* It drops rows with blank values and duplicate rows. Neither applied to this dataset, so all 100 rows remain.
4. *Calculates metrics:*
   - Total revenue
   - Revenue by product, with the best-selling product
   - Average order value
   - Revenue by region, with the top region
5. *Writes analysis_report.md* with an overview, the key metrics, and a limitations section.

## Results

| Metric | Value |
|---|---|
| Total revenue | 12,365,048 |
| Best-selling product | Laptop (3,889,210) |
| Average order value | 123,650.48 |
| Top region | North (3,983,635) |

## Testing Evidence

The script was run in Google Colab from a fresh session, using Runtime → Restart session followed by Runtime → Run all. Every cell ran without errors, and the output matched the figures above. Screenshots of each stage are in the screenshots/ folder.

## Technical Details

- *Language:* Python 3
- *Library:* pandas 2.2.3
- *Methods used:* read_csv, isna, duplicated, dropna, drop_duplicates, groupby, sum, mean, idxmax

## Limitations
- Unit prices vary widely within each product. For example, Headphones range from 4,195 to 49,930. This is unusual for real products and suggests the data is synthetic, so the results should be treated as practice, not business conclusions.
- Each customer appears in only one transaction, so repeat-purchase behaviour cannot be analysed.

- Unit prices vary widely within each product. For example, Headphones range from 4,195 to 49,930. This is unusual for real products and suggests the data is synthetic, so the results should be treated as practice, not business conclusions.
- Each customer appears in only one transaction, so repeat-purchase behaviour cannot be analysed.
