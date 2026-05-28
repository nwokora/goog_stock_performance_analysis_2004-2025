# 💹 Analysis of Google (GOOG) Stock Performance from 2004 to 2025.
This comprehensive analysis of Alphabet Inc.'s daily OHLCV stock (GOOG) reveals a remarkable 21-year growth trajectory that saw the shares move from ~2.50 (August 19, 2004) to ~200 in 20 years (August 19, 2004 to August 2025), after it first entered its Initial Public Offering (IPO) on August 19, 2004.  
It further narrows down the trend to mirror the 3 massive market crashes of the 2008 crisis, the COVID chaos, and the 2022 bear market.  
Skills demonstrated include: data import/cleanup, crisis performance insights, clean matplotlib visualizations, as well as critical thinking and problem-solving, ideal for financial analysis insights.

## 📂 Repository Layout  
- **🗄️ dataset** – Raw dataset and cleaned CSV files 
- **📈 analysis charts** – Final analysis visuals (PNG)
- **⚙️ process charts** – Technical work steps visual (PNG) 
- **💡 insights.md** – All insights from analysis
- **📉 Analysis Findings** – All metrics and findings from the analysis
- **📖 README.md** – Project overview

## 💡 Key Insights
Since its 2004 IPO, GOOG traded 584 billion shares over 5,478 sessions peaking at 18.5% volume in 2005 before troughing to 0.64% in low-turnover 2025 (daily volume down from 429M to 19M), while delivering 46x price growth (3.85 to 177.86, +4,520%), with 50.8% higher closes, and 1.93% volatility which signals scalable resilience amid crisis, especially the COVID crisis.
**[See Insights](https://github.com/nwokora/2004-to-2025-google-stock-analysis/blob/main/insights.md)**

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

## 📉 Analysis Findings
key data points and metrics extracted from the KO analysis.
**[See Findings](https://github.com/nwokora/2004-to-2025-google-stock-analysis/blob/main/analysis_findings.md)**

## 📈 Analysis Charts
This folder holds all the final charts and visualizations created from this analysis.
These include resistance trends over time, comparisons by gender, age group, and bacterial species. View charts here:
**[See Charts](https://github.com/nwokora/2004-to-2025-google-stock-analysis/tree/main/analysis_charts)**

## ⚙️ Process Charts
Work-in-progress charts showing screenshots of analysis steps.
**[See Charts](https://github.com/nwokora/2004-to-2025-google-stock-analysis/tree/main/process_charts)**

## 🗄️ Dataset
**Raw Dataset** – Original KO stock data (1962-2022): open, high, low, close prices + daily volume (~15K trading days).  
**Cleaned Dataset** – Processed CSVs with optimised data types for Power BI analysis.
**[Dataset](https://github.com/nwokora/2004-to-2025-google-stock-analysis/tree/main/dataset)**

## 🔗 Data Source
Google Stock Dataset (2004–2025) by MuqadasEjaz and collaborators on Kaggle (5,279 rows × 7 columns).
**[Download Dataset](https://www.kaggle.com/datasets/muqaddasejaz/google-stock-dataset-20042025)**







# 💹 Global Fuel Prices Analysis (2020-2026)

## 📌 Overview
This comprehensive analysis of Alphabet Inc.'s daily OHLCV stock (GOOG) reveals a remarkable 21-year growth trajectory, with shares rising from ~2.50 at its IPO on August 19, 2004, to ~200 by August 2025. The analysis mirrors how the stock performed through three major market downturns: the 2008 financial crisis, the COVID-19 market chaos, and the 2022 bear market.

Skills demonstrated include data import and cleanup, crisis-performance analysis, clean matplotlib visualizations, and critical thinking and problem-solving.

## 🎯 Objective
To analyze GOOG’s 21-year price performance from its IPO in 2004 through 2025, quantify its long-term growth, and evaluate how the stock fared during three major market crises (2008, COVID-19, and 2022) to assess its resilience and investment potential.

## 📊 Analysis Questions
1. Total Trading Volume by Year.
2. Average Daily Trading Volume by Year.
3. Average Closing Price by Year.
4. Average Daily Return by Year.
5. Average Daily Return by Month.
6. Closing Price with Major Stress Periods Highlighted.
   
## 🛠️ Tools Used
-  Excel (Initial data preview and quick validation of rows & columns distributions)
-  Python – Pandas (data cleaning & preparation) and Matplotlib (visualization)

## 🔗 Data Source
Google Stock Dataset (2004–2025) by MuqadasEjaz and collaborators on Kaggle (5,279 rows × 7 columns).
**[Download Dataset](https://www.kaggle.com/datasets/muqaddasejaz/google-stock-dataset-20042025)**

## 🧹 Data Cleaning and Preparation
- Datetime standardization `df["date"] = pd.to_datetime(df["date"]`
- Date column indexing `df = df.set_index("date").sort_index()`
- Checked for missing values (none were found) `df.isna().sum()`
- Checked for duplicates (none were found) `df.index.duplicated().sum()`
- Daily price range calculation `df["range"] = df["high"] - df["low"]`
- Year column creation `df["Year"] = df.index.year`
- Total Trading Days `days = np.busday_count('2004-08-19','2025-08-19')`
- Win Rate Percentage (close > open) `df['Win'] = df['close'] > df['open']
  win_rate = df['Win'].mean() * 100`
- Daily Volatility `daily_volatility = df['return'].std() * 100`

## 📉 Analysis
- **Total Trading Days** – This analysis shows the total trading days covered in the dataset, giving a total of 5,478 days.
- **Win Rate Percentage (close > open)** – This analysis shows the percentage of the time the stock closed higher than it opened; the win rate came at at 50.8&, indicating a better gain.
- **Average Daily Volatility** – This analysis reflects the typical day-to-day price fluctuation over the 21-year period. GOOG’s average daily volatility is 1.93%.
- **Total Trading Volume by Year** – This analysis examines GOOG's total trading volume, showing that the highest-volume year was 2005 with 108,150,653,430 shares, the lowest-volume year was 2025 with 3,745,998,200 shares, and the total shares traded across all years were 584,601,658,779.
- **Average Daily Trading Volume by Year** – This analysis examines GOOG's average daily trading volume each year over the 21-year period, showing that the highest average daily volume was in 2005 with 429,169,260 shares/day and the lowest was in 2024 with 19,702,144 shares/day.
- **Average Closing Price by Year** – This analysis tracks GOOG's average closing price each year from 2004 to 2025, revealing a strong upward trend from the lowest yearly average of 3.85 to the highest yearly average of 177.86.
- **Average Daily Return by Year** – This analysis calculates GOOG's average daily return for each year from 2004 to 2025, showing that the best year was 2004 with an average daily return of +0.0071, while the worst was 2008 at -0.0026. The years 2014 and 2022 also posted negative average daily returns, similar to 2008.
- **Average Daily Return by Month** – This analysis examines GOOG's average daily return for each month across the 21-year period, revealing that October delivers the strongest performance with an average daily return of +0.0037, while February performs the weakest at -0.0014.

## 🔭 Visualizations
<img width="627" height="254" alt="Average Fuel Price by Region" src="https://github.com/user-attachments/assets/d182547e-5dd3-4fd3-8ae9-3f1d0985add8" />   

**Average fuel prices varied widely by region, with Oceania and Europe recording the highest values overall. The Middle East had the lowest average fuel price, while South America and Africa also had relatively low prices.**

<img width="627" height="254" alt="Average Tax Percentage by Region" src="https://github.com/user-attachments/assets/bc877c97-3214-4388-8399-2d40f03572f1" />   

**Average tax percentages also differed noticeably by region. Oceania and Europe generally had the highest tax burdens, while South America had the lowest average tax percentage, followed by the Middle East.**

<img width="906" height="256" alt="Subsidy Charts" src="https://github.com/user-attachments/assets/e207c749-ec55-4400-bfb4-7cef93a42453" />

**The Middle East stands out with the highest average subsidy, and that matches its high share of Very High subsidy levels, while South America and Africa also show relatively stronger support than most regions. At the other end, Europe and especially Oceania have the lowest average subsidies, with Oceania being entirely in the Low subsidy category and Europe also heavily concentrated there. Overall, the pattern suggests that subsidy support is much stronger in the Middle East and weaker in Europe and Oceania.**

<img width="629" height="255" alt="Share_pct by Region and Income-level" src="https://github.com/user-attachments/assets/baf4febd-65f2-48d7-ba8c-71246bd0bdba" />

**Oceania is the most concentrated in the High category, with Europe and North America also leaning strongly toward High. In contrast, Africa is mostly in the Low category, and South America dominates the Middle level. Asia shows a more mixed split across the three categories, while the Middle East shows a split only between Middle and High, with High making up the larger portion.**

## 💡 Key Insights
Fuel affordability varies significantly across continental regions and countries from 2020 to 2026. The analysis shows that Europe and Oceania generally face the highest fuel prices and tax burdens. At the same time, the Middle East and South America record the lowest prices, probably due to strong subsidy support and low taxes. Regions like Oceania, Europe, and North America, with stronger income concentration, are better positioned to absorb the brunt of these low subsidies and high taxes, while Africa may likely face greater affordability pressure due to low income. Overall, fuel affordability is shaped by the combined impact of prices, taxes, subsidies, and income levels, with the greatest strain falling on specific regions and countries that are most exposed to these pressures. Policymakers should therefore balance taxation with targeted subsidies, especially in lower-income regions, to improve affordability.
**[See All Insights](https://github.com/nwokora/2020-2026_global_fuel_prices_analysis/blob/main/insights.md)**

## 📂 Repository Layout  
- **📈 analysis charts** – Final analysis visuals (PNG)
- **🗄️ dataset** – Raw dataset and cleaned CSV files
- **📋 group tables** – Pandas aggregated tables in CSV files
- **⚙️ process charts** – Technical work steps visual (PNG)
- **📖 README.md** – Project overview
- **🔎 Analysis Findings** – All metrics and findings from the analysis
- **💡 insights.md** – All insights from analysis
