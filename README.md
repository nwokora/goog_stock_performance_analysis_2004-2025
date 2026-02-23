# MultiHospital-HealthcareEDA

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
This analysis of 55,500 patient records (54,966 after deduplication) from thousands of hospitals reveals how medical conditions influence patient volumes and how factors such as blood type, age, and gender impact their prevalence. It also helps to understand the operational bottlenecks, demographic patterns, and hospital performance to boost clinical efficiency and optimisation.

## Files Provided
**Post-Cleaning**: 54,966 rows (534 duplicates removed), and 17 columns (Admission_ID and Length of Stay added)    
**Files Provided**:
- **Original Dataset**: (55,500 rows and 15 columns - original) [Download](https://www.kaggle.com/datasets/prasad22/healthcare-dataset)
- **Post-Cleaning**: (54,966 rows and 17 columns - analysis-ready)[Download](./Healthcare_dataset_cleaned.csv)
- Data Dictionary.md` (column definitions + cleaning notes)

## Data Sources
A synthetic healthcare dataset containing 55,500 patient records across 15 columns, including medical condition, hospital, doctor, test result, etc., by [**Prasad Patil**](https://www.kaggle.com/prasad22).

## Tools Used
**Excel** 
- Initial data preview and exploration
- Quick validation of column distributions

**Python**
- `pandas` (data cleaning: 55,500 → 54,966 rows deduplicated, groupby analysis)
- `matplotlib` (visualisations for all 10 questions)

**Workflow**: Excel preview → Python cleaning → Pandas analysis → Matplotlib charts

## Data Cleaning and Preparation
**Raw dataset**: 5279 rows × 7 columns (pre-wrangling).  
**Processed dataset**: 5279 rows, and 11 columns(4 added).

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
| **Q2** | **GOOG's closing price evolution from IPO (2004) to 2025, including performance during major stress periods like the 2008 crisis, 2020 COVID crash, and 2022 bear market?** | A: MA20 > MA50 = Yes, bullish trend confirmed |
| **Q3** | **Which year had the highest average daily trading volume for GOOG shares, and why?** | A: 0 missing values, 0 duplicates = Dataset reliable |
| **Q4** | **How do GOOG's average daily returns vary by month across 2004-2025?** | A: Volume spikes align with 5%+ return days = News/earnings driven |
| **Q5** | **How do GOOG's 20-day and 50-day moving averages reveal short-term trends and trading signals from 2020-2025?** | A: |


## Recommendations
Multiple synthetic artefacts invalidate it for real-world healthcare insights; therefore, the dataset should not qualify for any serious healthcare analysis or modelling.



## Visualizations
### 📊 Visualizations
<details>
<summary>Click to see chart insights</summary>

| Chart | Key Insight |
|-------|-------------|
| Patient Volume | Hospital A leads with 25% total admissions |
| LoS by Condition | Arthritis: longest average stay |
| Arthritis Demographics | Peaks 30-70, drops after 70 (data anomaly) |
</details>

![Patient Volume](figures/q1_patient_volume.png) ![LoS by Condition](figures/q3_los_condition.png)  
![Arthritis Demographics](figures/q5_arthritis_demo.png)

**Complete analysis**: `Healthcare_Analysis.ipynb` (interactive charts + code)

## Author
[LinkedIn](https://www.linkedin.com/in/somadina-nwokora/)
