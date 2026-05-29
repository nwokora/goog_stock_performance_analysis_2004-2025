# 💹 GOOG Stock Performance Analysis (2004-2025)

## 📌 Overview
This comprehensive analysis of Alphabet Inc.'s daily OHLCV stock (GOOG) reveals a remarkable 21-year growth trajectory, with shares rising from ~2.50 at its IPO on August 19, 2004, to ~200 by August 2025. The analysis mirrors how the stock performed through three major market downturns: the 2008 financial crisis, the COVID-19 market chaos, and the 2022 bear market.

Skills demonstrated include data import and cleanup, crisis performance analysis, clean Matplotlib visualisations, and critical thinking and problem-solving.

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
- **Closing Price with Major Stress Periods Highlighted** –

## 🔭 Visualizations
<img width="1024" height="409" alt="03_goog_total_trading_volume_by_year" src="https://github.com/user-attachments/assets/c4d2b0e3-0e54-4f37-9552-ef7dcd95c341" />

**Total Trading Volume by Year reveals how GOOG's trading activity evolved over the 21-year period from 2004 to 2025. The highest-volume year was 2005 with 108,150,653,430 shares traded, while the lowest-volume year was 2025 with 3,745,998,200 shares. Across all years, a total of 584,601,658,779 shares were traded. Overall, the pattern shows that trading volume was extremely high in the early years following GOOG's IPO, particularly in 2005, and has generally declined in more recent years.**

<img width="1038" height="446" alt="05_goog_average_closing_price_by_year" src="https://github.com/user-attachments/assets/8968a1b3-58ac-4918-ab45-eaf543b2a282" />
   
**Average Closing Price by Year shows the lowest yearly average closing price was 3.85, while the highest was 177.86. Overall, the pattern shows a strong and consistent upward trend, with GOOG's price climbing dramatically from its early years after the IPO to much higher levels by the end of the period.**

<img width="962" height="354" alt="Screenshot 2026-05-29 125650" src="https://github.com/user-attachments/assets/9fbefec4-1e1f-4da8-acaa-f7cd52e91b22" />

**2004 delivered GOOG's highest average daily return at +0.0071 (0.71%), while 2008 recorded the lowest at -0.0026 (-0.26%). 2022 also posted a negative average daily return. These negative years align with major market stress periods: the 2008 financial crisis and the 2022 bear market, which was exacerbated by post-COVID-19 economic adjustments. Rather than undermining confidence, these downturns actually highlight GOOG's resilience; the stock recovered strongly after both crises and continued its upward trajectory.**

<img width="979" height="443" alt="07_goog_average_daily_return_by_month" src="https://github.com/user-attachments/assets/e4b2068c-db32-4289-8dee-748b5303935a" />

**Average Daily Return by Month reveals that the highest return month is October with an average daily return of +0.0037 (0.37%), while the lowest return month is February at -0.0014 (-0.14%). Overall, GOOG tends to perform better in the fall months, particularly October, while early-year months like February tend to show weaker or negative returns, indicating some seasonal variation in the stock's performance.**

## 💡 Key Insights
Fuel affordability varies significantly across continental regions and countries from 2020 to 2026. The analysis shows that Europe and Oceania generally face the highest fuel prices and tax burdens. At the same time, the Middle East and South America record the lowest prices, probably due to strong subsidy support and low taxes. Regions like Oceania, Europe, and North America, with stronger income concentration, are better positioned to absorb the brunt of these low subsidies and high taxes, while Africa may likely face greater affordability pressure due to low income. Overall, fuel affordability is shaped by the combined impact of prices, taxes, subsidies, and income levels, with the greatest strain falling on specific regions and countries that are most exposed to these pressures. Policymakers should therefore balance taxation with targeted subsidies, especially in lower-income regions, to improve affordability.

For long-term investors, this pattern reinforces GOOG's appeal: while it experiences temporary drawdowns during systemic stress, its ability to rebound and sustain growth over time makes it a solid choice for 
**[See All Insights](https://github.com/nwokora/2020-2026_global_fuel_prices_analysis/blob/main/insights.md)**

## 📂 Repository Layout  
- **📈 analysis charts** – Final analysis visuals (PNG)
- **🗄️ dataset** – Raw dataset and cleaned CSV files
- **📋 group tables** – Pandas aggregated tables in CSV files
- **⚙️ process charts** – Technical work steps visual (PNG)
- **📖 README.md** – Project overview
- **🔎 Analysis Findings** – All metrics and findings from the analysis
- **💡 insights.md** – All insights from analysis
