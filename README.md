# MultiHospital-HealthcareEDA

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools Used](#tools-used)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis and Data Analysis](#exploratory-data-analysis-and-data-analysis)
- [Analysis Findings](#analysis-findings)
- [Insights and Recommendations](#insights-and-recommendations)
  
## Project Overview
This analysis of 55,500 patient records (54,966 after deduplication) from thousands of hospitals reveals how medical conditions influence patient volumes and how factors such as blood type, age, and gender impact their prevalence. It also helps to understand the operational bottlenecks, demographic patterns, and hospital performance to boost clinical efficiency and optimisation.

## Data Sources
**Dataset**: Synthetic Healthcare Patient Records Dataset by [**Prasad Patil**](https://www.kaggle.com/prasad22).  
**Post-Cleaning**: 54,966 rows (534 duplicates removed), and 17 columns (Admission_ID and Length of Stay added)  
**License**: [CC0/Public Domain - specify if known, or "synthetic dataset for portfolio demonstration"]  
**Original Source**: [Kaggle/Synthetic/Your description - e.g., "Generated for healthcare analytics training"]  
**Files Provided**:
- `Healthcare_Dataset.csv` (55,500 rows and 15 columns - original) [Download](https://www.kaggle.com/datasets/prasad22/healthcare-dataset)
- `Healthcare_cleaned.csv` (54,966 rows and 17 columns - analysis-ready)
- `data_dictionary.md` (column definitions + cleaning notes)

## Tools Used
**Excel** 
- Initial data preview and exploration
- Quick validation of column distributions

**Python**
- `pandas` (data cleaning: 55,500 → 54,966 rows deduplicated, groupby analysis)
- `matplotlib` (visualisations for all 10 questions)

**Workflow**: Excel preview → Python cleaning → Pandas analysis → Matplotlib charts

## Data Cleaning and Preparation
**Raw Dataset**: 55,500 rows × 15 columns  
**Clean Dataset**: 54,966 rows (534 duplicates = **0.96%** improvement), and 17 columns.

### Key Cleaning Steps:

**Column Standardisation**
- Numeric/Date columns: Type conversion (`Age`, `Billing Amount`, Date of Admission, `Discharge Date)
- Name column: Consistent formatting
- Categorical: Trimmed whitespace (Medical Condition, Blood Type, etc.)

**Duplicate Detection**
- Generated `Unique_ID` by concatenating: Name + Age + Gender + Blood Type + Date of Admission + Hospital + Discharge Date
- Found & removed 534 duplicates → 54,966 unique patient records
- Reset index + assigned `Admission_ID` as final unique identifier

**Outlier Treatment (Domain-Driven)**
   | Column | Issue | Treatment | Rationale |
   |--------|-------|-----------|-----------|
   | Age | None | None | All values realistic (0-120) |
   | Billing Amount | 106 negative values | Flagged as refunds | Common in healthcare datasets |

**Feature Engineering**
- **Calculated Length of Stay (LoS)**: Discharge Date - Admission Date
- Dropped temporary `Unique_ID` column

**✅ Validation**: No missing values detected. All distributions are realistic for the healthcare domain.

**Full pipeline**: `01_data_cleaning.py` (reproducible + commented)

## Exploratory Data Analysis and Data Analysis

**Dataset Analyzed**: 54,966 cleaned patient records × 39,876 hospitals  
**Objective**: Systematically answer 10 core business questions

### Technical Approach

**Univariate Analysis**
- Distribution analysis by Medical Condition, Age, Gender, Blood Type
- Summary statistics (mean, counts) for LoS, Billing Amount
- Frequency tables for categorical variables

**Bivariate Analysis** 
- Cross-tabulations: Condition × Age Bracket, Condition × Gender
- Groupby operations: Hospital volume by condition
- Pivot tables: Admission Type proportions

**Time-Series Analysis**
- LoS trends over admission dates
- Temporal patterns in emergency vs elective admissions

**Analytical Methods Used**

## Analysis Findings
### 10 Business Questions Answered

| Q# | Question | Key Finding |
|----|----------|-------------|
| Q1 | Medical Condition vs Age Distribution of Patients | **Asthma dominates caseload** Top condition by hospital density: Arthritis (16.9% of admissions) |
| Q2 | Which Blood Type Correlates with the Highest Diabetes Prevalence? | **A+ highest prevalence (13%)** |
| Q3 | How does the average Length of Stay (LoS) vary by medical condition, and which has the highest? | **Asthma: 15.7 days** |
| Q4 | How are test result categories (Abnormal, Inconclusive, Normal) distributed as percentages across medical conditions? | **Hypertension: 33.5%** |
| Q5 | What Age-Gender Bracket Peaks in Arthritis Cases? | **30-50 Female (1,391 cases)** |
| Q6 | Top 10 Hospitals by Admission Volumes? | **Volume leaders identified** |
| Q7 | Medical Conditions by Hospital Density? | **Condition specialization patterns** |
| Q8 | Top 5 Insurance Providers? | **Market share distribution** |
| Q9 | Patients by Admission Type? | **Emergency/Elective proportions** |
| Q10| Average Length of Stay Trend Over Time? | **Temporal efficiency patterns** |

## Insights and Recommendations
- **Asthma crisis**: Highest volume + longest stays = operations bottleneck
- **Hypertension testing**: 33.5% inconclusive = diagnostic urgency  
- **Arthritis demographics**: 30-50yo women peak = targeted screening
- **System fragmentation**: 39K hospitals averaging 1.4 patients each

### 📊 Visualizations
![Patient Volume](figures/q1_patient_volume.png) ![LoS by Condition](figures/q3_los_condition.png)  
![Arthritis Demographics](figures/q5_arthritis_demo.png)

**Complete analysis**: `Healthcare_Analysis.ipynb` (interactive charts + code)
