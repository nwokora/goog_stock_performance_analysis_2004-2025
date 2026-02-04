# MultiHospital-HealthcareEDA
## Project Overview
This analysis of 55,500 patient records (54,966 after deduplication) from thousands of hospitals reveals how medical conditions influence patient volumes and how factors such as blood type, age, and gender impact their prevalence. It also helps to understand the operational bottlenecks, demographic patterns, and hospital performance to boost clinical efficiency and optimisation.
## Data Sources
**Dataset**: Synthetic Healthcare Patient Records Dataset by [**Prasad Patil**](https://www.kaggle.com/prasad22).  
**Post-Cleaning**: 54,966 rows (534 duplicates removed), and 17 columns (Admission_ID and Length of Stay added)  
**License**: [CC0/Public Domain - specify if known, or "synthetic dataset for portfolio demonstration"]  
**Original Source**: [Kaggle/Synthetic/Your description - e.g., "Generated for healthcare analytics training"]  
**Files Provided**:
- [`Healthcare_Dataset.csv`](https://www.kaggle.com/datasets/prasad22/healthcare-dataset) (55,500 rows and 15 columns - original)
- [`Healthcare_cleaned.csv`](Healthcare_cleaned.csv…) (54,966 rows and 17 columns - analysis-ready)
- `data_dictionary.md` (column definitions + cleaning notes)
- ## Tools Used
**Excel** 
- Initial data preview and exploration
- Quick validation of column distributions

**Python**
- `pandas` (data cleaning: 55,500 → 54,966 rows deduplicated, groupby analysis)
- `matplotlib` (visualisations for all 10 questions)

**Workflow**: Excel preview → Python cleaning → Pandas analysis → Matplotlib charts
## Data Cleaning/Preparation
**Raw Dataset**: 55,500 rows × 15 columns  
**Clean Dataset**: 54,966 rows (534 duplicates = **0.96%** improvement), and 17 columns.

### Key Cleaning Steps:

1. **Column Standardization**
   - Numeric/Date columns: Type conversion (`Age`, `Billing Amount`, Date of Admission, `Discharge Date)
   - Name column: Consistent formatting
   - Categorical: Trimmed whitespace (Medical Condition, Blood Type, etc.)

2. **Smart Duplicate Detection**
   - Generated `Unique_ID` by concatenating: Name + Age + Gender + Blood Type + Date of Admission + Hospital + Discharge Date
   - **Found & removed 534 duplicates** → 54,966 unique patient records
   - Reset index + assigned `Admission_ID` as final unique identifier

3. **Outlier Treatment (Domain-Driven)**
   | Column | Issue | Treatment | Rationale |
   |--------|-------|-----------|-----------|
   | Age | None | None | All values realistic (0-120) |
   | Billing Amount | 106 negative values | Flagged as refunds | Common in healthcare datasets |

4. **Feature Engineering**
   - **Calculated Length of Stay (LoS)**: Discharge Date - Admission Date
   - Dropped temporary `Unique_ID` column

**✅ Validation**: No missing values detected. All distributions are realistic for the healthcare domain.

**Full pipeline**: `01_data_cleaning.py` (reproducible + commented)
## Exploratory Data Analysis and Data Analysis

**Dataset Analyzed**: 54,966 cleaned patient records × 39,876 hospitals  
**Objective**: Systematically answer 10 core business questions

### Technical Approach

**1. Univariate Analysis**
- Distribution analysis by Medical Condition, Age, Gender, Blood Type
- Summary statistics (mean, counts) for LoS, Billing Amount
- Frequency tables for categorical variables

**2. Bivariate Analysis** 
- Cross-tabulations: Condition × Age Bracket, Condition × Gender
- Groupby operations: Hospital volume by condition
- Pivot tables: Admission Type proportions

**3. Time-Series Analysis**
- LoS trends over admission dates
- Temporal patterns in emergency vs elective admissions

**4. Analytical Methods Used**
## Results/Findings
### 10 Business Questions Answered

| Q# | Question | Key Finding |
|----|----------|-------------|
| Q1 | Highest Patient Volume | **Asthma dominates caseload** |
| Q2 | Blood Type + Diabetes| **A+ highest prevalence (13%)** |
| Q3 | Longest Avg LoS | **Asthma: 15.7 days** |
| Q4 | Highest Inconclusive Tests | **Hypertension: 33.5%** |
| Q5 | Arthritis Peak Bracket | **30-50 Female (1,391 cases)** |
| Q6 | Top 10 Hospitals | **Volume leaders identified** |
| Q7 | Hospital Density | **Condition specialization patterns** |
| Q8 | Top 5 Insurers | **Market share distribution** |
| Q9 | Admission Types | **Emergency/Elective proportions** |
| Q10| LoS Time Trends | **Temporal efficiency patterns** |

### 🎯 Major Insights
- **Asthma crisis**: Highest volume + longest stays = operations bottleneck
- **Hypertension testing**: 33.5% inconclusive = diagnostic urgency  
- **Arthritis demographics**: 30-50yo women peak = targeted screening
- **System fragmentation**: 39K hospitals averaging 1.4 patients each

### 📊 Visualizations
![Patient Volume](figures/q1_patient_volume.png) ![LoS by Condition](figures/q3_los_condition.png)  
![Arthritis Demographics](figures/q5_arthritis_demo.png)

**Complete analysis**: `Healthcare_Analysis.ipynb` (interactive charts + code)
