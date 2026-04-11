# 💹 Analysis of Google (GOOG) Stock Performance from 2004 to 2025.
This comprehensive analysis of Alphabet Inc.'s daily OHLCV stock (GOOG) reveals a remarkable 20-year growth trajectory that saw the shares move from ~2.50 (August 19, 2004) to ~200 in 20 years (August 19, 2004 to August 2025), after it first entered its Initial Public Offering (IPO) on August 19, 2004.  
It further narrows down the trend to mirror the 3 massive market crashes of the 2008 crisis, the COVID chaos, and the 2022 bear market.  
Skills demonstrated include: data import/cleanup, crisis performance insights, clean matplotlib visualizations, as well as critical thinking and problem-solving, ideal for financial analysis insights.

## 📂 Repository Layout  
- **🗄️ dataset** – Raw dataset and cleaned CSV files 
- **📈 analysis charts** – Final analysis visuals (PNG)
- **⚙️ process charts** – Technical work steps visual (PNG) 
- **💡 insights.md** – All insights from analysis 
- **📖 README.md** – Project overview 

  ## 🛠️ Tools Used
-  **Excel** – Initial data preview and quick validation of rows & columns distributions
-  **Python** – Pandas (data cleaning & preparation) and Matplotlib (visualization)
-  **GitHub** – Hosting documented projects
-  **Markdown** – Documentation (.md files)

 ## 🧠 Skills Demonstrated
- Data transformation from raw to cleaned datasets using pandas
- Datetime standardization `df["date"] = pd.to_datetime(df["date"])`
- Date series indexing and chronological sorting `df = df.set_index("date").sort_index()`
- Missing value detection `df.isna().sum()`
- Duplicate index detection `df.index.duplicated().sum()`
- Daily price range calculation `df["range"] = df["high"] - df["low"]`
- Financial chart visualization of historical stock performance using Matplotlib
- Problem-solving to match and analyze aggregation trends

## 📊 Business Questions Answered
1. Total Trading Volume by Year
2. Average Daily Trading Volume by Year
3. Average Closing Price by Year
4. Average Daily Return by Year
5. Average Daily Return by Month
6. Closing Price with Major Stress Periods Highlighted

## 💡 Key Insights
Since its 2004 IPO, GOOG traded 584 billion shares over 5,478 sessions peaking at 18.5% volume in 2005 before troughing to 0.64% in low-turnover 2025 (daily volume down from 429M to 19M), while delivering 46x price growth (3.85 to 177.86, +4,520%), with 50.8% higher closes, and 1.93% volatility which signals scalable resilience amid crisis, especially the COVID crisis.
**[See Insights](https://github.com/nwokora/2004-to-2025-google-stock-analysis/blob/main/insights.md)**

## 📉 Analysis Findings
key data points and metrics extracted from the KO analysis.
**[See Findings](https://github.com/nwokora/2004-to-2025-google-stock-analysis/blob/main/analysis_findings.md)**

## ⚙️ Process Charts
Work-in-progress charts showing screenshots of analysis steps.
**[See Charts](https://github.com/nwokora/2004-to-2025-google-stock-analysis/tree/main/process_charts)**

## 📈 Analysis Charts
This folder holds all the final charts and visualizations created from this analysis.
These include resistance trends over time, comparisons by gender, age group, and bacterial species. View charts here:
**[See Charts](https://github.com/nwokora/2004-to-2025-google-stock-analysis/tree/main/analysis_charts)**

## 🗄️ Dataset
**Raw Dataset** – Original KO stock data (1962-2022): open, high, low, close prices + daily volume (~15K trading days).  
**Cleaned Dataset** – Processed CSVs with optimised data types for Power BI analysis.
**[Dataset](https://github.com/nwokora/2004-to-2025-google-stock-analysis/tree/main/dataset)**

## 🔗 Data Source
Google Stock Dataset (2004–2025) by MuqadasEjaz and collaborators on Kaggle (5,279 rows × 7 columns).
**[Download Dataset](https://www.kaggle.com/datasets/muqaddasejaz/google-stock-dataset-20042025)**
