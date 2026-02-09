# MultiHospital-HealthcareEDA

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools Used](#tools-used)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis and Data Analysis](#exploratory-data-analysis-and-data-analysis)
- [Analysis Findings](#analysis-findings)
- [Insights and Recommendations](#insights-and-recommendations)
- [Author](author)
  
## Project Overview
This analysis of 55,500 patient records (54,966 after deduplication) from thousands of hospitals reveals how medical conditions influence patient volumes and how factors such as blood type, age, and gender impact their prevalence. It also helps to understand the operational bottlenecks, demographic patterns, and hospital performance to boost clinical efficiency and optimisation.

## Data Sources
**Dataset**: A synthetic healthcare dataset containing 55,500 patient records across 15 columns, including medical condition, hospital, doctor, test result, etc., by [**Prasad Patil**](https://www.kaggle.com/prasad22).
**Post-Cleaning**: 54,966 rows (534 duplicates removed), and 17 columns (Admission_ID and Length of Stay added)    
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
| Q1 | Medical Condition vs Age Distribution of Patients | • Pediatrics (0-17) represent ~2-3% of hospital admissions, although adult-onset conditions like hypertension(11), diabetes(16), and arthritis(21) are rare in pediatric cases. <br>• Arthritis dominates overall volume (9218 patients) but shows balanced age distribution. |
| Q2 | Which Blood Type Correlates with the Highest Diabetes Prevalence? | A+ blood type takes the lead with 13%, but uniform diabetes distribution across blood types (12.0-13.0%) shows no significant blood type-diabetes correlation in the dataset. |
| Q3 | How does the average Length of Stay (LoS) vary by medical condition, and which has the highest? | Shows uniform average LoS of 15 days across medical conditions. (Higher than expected).  |
| Q4 | How are test result categories (Abnormal, Inconclusive, Normal) distributed as percentages across medical conditions? | All conditions have basically the same test result split, about 33% normal, 33% abnormal, 33% inconclusive. The perfect uniformity of the dataset shows a more synthetic nature than a real-life clinical dataset. |
| Q5 | What Age-Gender Bracket Peaks in Arthritis Cases? | Arthritis cases for both males and females are low under age 30, peak strongly between 30-70, then drop off after 70, which doesn't show real-world patterns where we would expect cases to stay high or rise in older age groups. |
| Q6 | Top 10 Hospitals by Admission Volumes? | Among the 39,876 hospitals treating our 54,966 patients, LLC Smith tops the list with just 44 admissions. This suggests most facilities handle only a handful of cases each. |
| Q7 | Medical Conditions by Hospital Density? | Medical conditions appear evenly spread (16%) across hospitals regardless of their size or location, which feels unrealistic. Real-world data would show bigger hospitals handling more complex cases like cancer.  |
| Q8 | Top 5 Insurance Providers? | The top 5 insurance providers are tightly spread: Cigna edges out at 20.3%, followed closely by Medicare (20.1%), UnitedHealthcare (20.0%), Blue Cross (19.9%), and Aetna (19.7%) |
| Q9 | Patients by Admission Type? | Admission types perfectly balanced at ~33% each. This uniform split confirms random assignment, not operational reality, where emergency, for instance, dominates the spread, and elective fills schedule slots. |
| Q10| Average Length of Stay Trend Over Time? | LoS stays around 15 days from 2019-2024, with 2024 just nudging toward 16th day |

## Insights and Recommendations
- **Asthma crisis**: Highest volume + longest stays = operations bottleneck
- **Hypertension testing**: 33.5% inconclusive = diagnostic urgency  
- **Arthritis demographics**: 30-50yo women peak = targeted screening
- **System fragmentation**: 39K hospitals averaging 1.4 patients each

### 📊 Visualizations
![Patient Volume](figures/q1_patient_volume.png) ![LoS by Condition](figures/q3_los_condition.png)  
![Arthritis Demographics](figures/q5_arthritis_demo.png)

**Complete analysis**: `Healthcare_Analysis.ipynb` (interactive charts + code)

## Author
[Somadina Nwokora](https://www.linkedin.com/in/somadina-nwokora/)
