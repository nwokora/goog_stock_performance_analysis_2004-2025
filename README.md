# 2004-2025 Google Stock Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Files Provided](#files-provided)
- [Data Sources](#data-sources)
- [Tools Used](#tools-used)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis and Data Analysis](#exploratory-data-analysis-and-data-analysis)
- [Analysis Findings](#analysis-findings)
- [Insights](#insights)
- [Recommendations](#recommendations)
- [Visualizations](#visualizations)
- [Author](#author)

## Project Overview
Comprehensive analysis of Alphabet Inc. (GOOG) daily OHLCV stock data spanning the complete post IPO history (Aug 19, 2004 - Aug 2025). This project shows the stock volatility over 20 years, and Tracked GOOG through 3 massive market crashes of 2008 meltdown, COVID chaos, and 2022 bear market

Skills demonstrated in this analysis include; data import and cleanup → crisis performance insights → clean matplotlib visualizations, and critical thinking, making it suitable for financial analytics tasks.

## Files Provided    

## Data Sources
2004-2025 Google Stock Dataset (5,279 rows × 7 columns) [Download](https://www.kaggle.com/datasets/muqaddasejaz/google-stock-dataset-20042025)

## Tools Used
**Excel** 
- Initial data preview and exploration
- Quick validation of column distributions

**Python**
- `pandas` (data cleaning and preparation)
- `matplotlib` (creates visualization)

**Workflow**: Excel preview → Python cleaning → Pandas analysis → Matplotlib charts

## Data Cleaning and Preparation

### Data Quality Check:

**Column Standardisation**
- Datetime standardisation `df["date"] = pd.to_datetime(df["date"])`  
  *Converts string dates to proper datetime objects*
- Date column indexing `df = df.set_index("date").sort_index()`  
  *Transforms date column into date index for analysis*  

**Missing Value Check**  
- Check for missing value `df.isna().sum()`.  
  *(All columns: No missing value)*  
  
**Duplicate Check**
- Index dates: `df.index.duplicated().sum()` → *0 (Unique dates)*
- Full rows:   `df.duplicated().sum()`     → *0 (No identical rows)*

### Feature Engineering  
- Daily price range `df["range"] = df["high"] - df["low"]`  
- Daily % price change `df["return"] = df["close"].pct_change()`  
- 20-day and 50-day Moving average `df["MA20"] = df["close"].rolling(window=20).mean()` and `df["MA50"] = df["close"].rolling(window=50).mean()`  

## Exploratory Data Analysis and Data Analysis  

**Analytical Methods Used**

| Method | Purpose | Implementation |
|--------|---------|----------------|
| **Descriptive Statistics** | Dataset overview | `df.describe()` |
| **Daily Returns** | Performance measurement | `df['close'].pct_change()` |
| **Moving Averages** | Trend identification | `rolling(20/50).mean()` |
| **Volatility Analysis** | Risk assessment | `std() × √252` (30.6% result) |
| **Data Quality Checks** | Reliability validation | `isna().sum()`, `duplicated()` |
| **Feature Engineering** | Enhanced analysis | Range, returns, MAs created |

**Key Financial Metrics Calculated:**


## Analysis Findings
### 5 Business Questions Answered
| Q | Question | Result |
|---| ---------|--------|
| **Q1** | **Which year saw the highest trading activity in GOOG shares, and what drove the volume spikes?** | 2005 saw the highest trading activity in GOOG shares (~108 billion), driven by the post-IPO rush. 2025 had the lowest (~4 billion) due to incomplete year data.|
| **Q2** | **Which year had the highest average daily trading volume for GOOG shares, and why?**  | 2005 dominated GOOG's average daily trading volume (429 million shares/day) due to post-IPO excitement, while 2024 had the lowest (20 million shares/day) amid stock maturity and splits. |
| **Q3** | **How do GOOG's average daily returns vary by month across 2004-2025?** | The monthly seasonality patterns of GOOG's 2004-2025 average daily returns show October as the strongest and February as the weakest. |
| **Q4** | **GOOG's closing price evolution from IPO (2004) to 2025, including performance during major stress periods like the 2008 crisis, 2020 COVID crash, and 2022 bear market?** | GOOG showed 82x growth from ~$2.50 (2004 IPO) to ~$204 (2025). Handled 2008 (-55%, quick bounce), 2020 COVID (-30%, sharp recovery), 2022 (-40%, steady climb back). |
| **Q5** | **How do GOOG's 20-day and 50-day moving averages reveal short-term trends and trading signals from 2020-2025?** | GOOG's 20-day and 50-day moving averages (MAs) reveal short-term trends through their direction and crossovers from 2020-2025. |


## Recommendations
Multiple synthetic artefacts invalidate it for real-world healthcare insights; therefore, the dataset should not qualify for any serious healthcare analysis or modelling.



## Visualizations




**Complete analysis**: `Healthcare_Analysis.ipynb` (interactive charts + code)

## Author
[LinkedIn](https://www.linkedin.com/in/somadina-nwokora/)
