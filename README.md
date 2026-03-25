# New Zealand National Accounts Analysis
### From Income to Investment: Sectoral Saving and Capital Allocation in New Zealand
**Stats NZ | National Accounts Income & Expenditure | Year Ended March 2025**



## Overview

This project is a full data science and machine learning analysis of New Zealand's national accounts, using official Statistics New Zealand (Stats NZ) data. The central goal is to trace how income is generated across the economy, how it is redistributed via taxes and transfers, how much is saved by each sector, and whether that saving is being effectively converted into productive investment and real capital accumulation.

The analysis spans data from as far back as 1972 through to the year ended March 2025, covering 44 research questions across 9 analytical modules.



## Research Objective

> *Trace how income is generated, redistributed, saved, and ultimately invested across sectors of the New Zealand economy thus linking financial flows to real capital accumulation.*



## Data Sources

All data is sourced from [Statistics New Zealand (Stats NZ)](https://www.stats.govt.nz/information-releases/national-accounts-income-and-expenditure-year-ended-march-2025) and follows the System of National Accounts 2008 (SNA 2008) standard.

| File | Description | Period |
|---|---|---|
| `na-nov2025-institutional-sector-accounts.csv` | Saving, income, GFCF, net lending/borrowing by sector | 1987–2024 |
| `na-nov2025-capital-stocks.csv` | Net capital stock, GFCF, depreciation by industry and asset type | 1972–2025 |
| `na-nov2025-gdp-breakdown.csv` | GDP by production, income, and expenditure measures | 1972–2024 |
| `na-nov2025-hce.csv` | Household final consumption expenditure by category | 1988–2024 |
| `na-nov2025-taxes.csv` | GST and tax type breakdown | 1987–2024 |
| `na-nov2025-agriculture.csv` | Agricultural output by commodity | 2007–2024 |
| `na-nov2025-per-capita.csv` | GDP per capita in NZD | 1992–2024 |



## Notebook Structure

The analysis is delivered as a single Google Colab notebook (`NZ_National_Accounts_Analysis.ipynb`) with approximately 95 cells across 9 modules.

| Module | Focus | Key Methods |
|---|---|---|
| **Setup (Cells 1–4)** | Libraries, data loading, master panel | pandas, numpy |
| **Module 1** | Income Generation & Distribution | Time series, stacked area, expenditure decomposition |
| **Module 2** | Saving Behaviour | STL decomposition, OLS regression, scatter analysis |
| **Module 3** | Sectoral Balances (Net Lending/Borrowing) | ADF stationarity test, Granger causality |
| **Module 4** | Investment & Capital Formation | K-Means clustering, PCA, GOS-GFCF regression |
| **Module 5** | Capital Stock & Productive Capacity | Net investment sufficiency, housing vs productive capital |
| **Module 6** | Saving–Investment Linkage | Feldstein-Horioka OLS, lead-lag analysis |
| **Module 7** | External Sector Dependence | STL trend, external balance decomposition |
| **Module 8** | Structural & Dynamic Analysis | ARIMA(1,1,1) forecasting, rolling correlation, COVID shock |
| **Module 9** | GDP Per Capita & Living Standards | Growth decomposition |



## Research Questions

The notebook was designed to answer 44 specific research questions across the following themes:

- **Sectoral balances**: Who saves, who borrows, and are imbalances structural or cyclical?
- **Saving behaviour**: How do household, business, and government saving rates evolve?
- **Investment alignment**: Does saving translate into capital formation, or does it leak elsewhere?
- **Capital stock**: Is New Zealand building enough productive capacity relative to its economic growth?
- **External dependence**: How much of domestic investment is funded by foreign capital?
- **Income redistribution**: What role do taxes, subsidies, and transfers play in shifting saving capacity?
- **Structural change**: Are observed patterns cyclical (temporary) or structural (persistent)?

**41 of 44 questions are fully answered.** The three not answered (Q12, Q32, Q44) require additional data on household debt, total factor productivity, and three-measure GDP reconciliation  which are not included in the source files.



## Methods & Tools

| Category | Tools Used |
|---|---|
| **Data wrangling** | `pandas`, `numpy` |
| **Visualisation** | `matplotlib`, `seaborn`, `plotly` |
| **Time series** | `statsmodels` STL, ARIMA, ADF test, Granger causality |
| **Machine learning** | `scikit-learn` K-Means clustering, PCA |
| **Econometrics** | OLS regression (Feldstein-Horioka, GOS-GFCF, lead-lag) |
| **Environment** | Google Colab (Python 3.10+) |



## How to Run

1. Download all 7 CSV files from the [Stats NZ website](https://www.stats.govt.nz/information-releases/national-accounts-income-and-expenditure-year-ended-march-2025)
2. Upload the CSVs to your Google Drive or directly to a Colab session
3. Open `NZ_National_Accounts_Analysis.ipynb` in Google Colab
4. In **Cell 1**, update `DATA_PATH` to point to your files:
   ```python
  
5. Run all cells sequentially 

The notebook will generate **18+ PNG charts** saved to your working directory.


## Key Outputs

- **18+ publication-quality charts** across all modules
- **Printed statistical summaries** for each module (correlations, regression coefficients, ADF test results)
- **ARIMA 5-year forecast** of the national saving rate
- **Industry investment clusters** (K-Means with PCA visualisation)
- **Executive summary table** with all key metrics for the latest year



## Limitations

- All monetary values are **nominal (current prices)**, real/inflation-adjusted analysis would require a price deflator series not included in this dataset.
- Household **debt and borrowing** data (Q12) is not in the institutional sector accounts data.
- **Total factor productivity** (Q32) is not derivable from these files alone.
- The analysis covers the **year ended March 2025** as the latest data point.



## License

Data is sourced from Statistics New Zealand under the [Creative Commons Attribution 4.0 International licence](https://creativecommons.org/licenses/by/4.0/). Code in this repository is released under the MIT License.





Analysis conducted using Python data science and econometric methods on Stats NZ public data.
Data source: [Stats NZ National Accounts](https://www.stats.govt.nz)
