# Depression_students
highlighting and address mental health challenges in students

# Student Depression Analysis

## Overview

This project explores a dataset focused on student mental health to identify patterns and potential factors contributing to depression. The goal is to uncover how academic pressure, lifestyle habits, financial stress, and demographics correlate with students' mental health—specifically, their depression status.

By conducting data cleaning, exploratory data analysis (EDA), statistical testing, and visualizations, we gain insights that may help in building support mechanisms for students facing mental health challenges.

---

## Dataset Information

- **File**: `student_depression_dataset.csv`
- **Target Column**: `Depression`  
  - Binary values: `0 = No`, `1 = Yes`
- **Features**:
  - Demographics: `Age`, `Gender`, `City`, `Degree`, etc.
  - Lifestyle: `Sleep Duration`, `Work/Study Hours`, etc.
  - Academic & Work Metrics: `Academic Pressure`, `Work Pressure`, `CGPA`, etc.
  - Mental Health Indicators: `Suicidal Thoughts`, `Family History of Mental Illness`
  - Satisfaction Scores: `Study Satisfaction`, `Job Satisfaction`
  - Stress: `Financial Stress`

---

## Tools & Technologies

- **Language**: Python
- **Libraries**:
  - `pandas`, `numpy` – data manipulation
  - `matplotlib`, `seaborn` – visualizations
  - `scipy.stats` – statistical testing

---

## Project Workflow

### 1. Data Cleaning & Preprocessing

- Removed irrelevant columns: `ID`, `Profession`
- Converted columns like `Gender`, `City`, `Degree`, `Family History of Mental Illness` to `category` data type
- Cleaned the `Sleep Duration` column (e.g., extracted numbers from text like “6 hours”)
- Handled missing values by imputing with **median** (e.g., for `Sleep Duration`)
- Converted the `Depression` column to integer type for analysis

### 2. Exploratory Data Analysis (EDA)

- Used countplots for categorical columns to view frequency distribution
- Histograms for numerical columns like `Age`, `CGPA`, `Work Pressure`
- Boxplots comparing depressed vs. non-depressed students for:
  - `Academic Pressure`
  - `Work Pressure`
  - `Total Pressure` (combined metric)
- Correlation heatmap to observe relationships among numerical variables

### 3. Feature Engineering

- Created a new column:  
  `Total Pressure = Academic Pressure + Work Pressure`

### 4. Statistical Testing

- Separated students based on depression status
- Performed:
  - **T-test** to compare means of `Academic Pressure` between groups
  - **Mann-Whitney U test** for robustness (non-parametric)
- Example result:
Depressed group size: 16,336
Non-depressed group size: 11,565
T-test statistic: 90.119, p-value: 0.000
Mann-Whitney U test statistic: 145,556,846.500, p-value: 0.000



### 5. Visualization Highlights

- Distribution of Depression status
- Depression count by gender
- Histograms of numerical features
- Boxplot: Total Pressure by Depression status
- Correlation matrix of numerical variables

---

## Key Insights

- Students with higher academic and work pressure are more likely to experience depression
- Lower sleep duration and financial stress correlate with increased depression risk
- Students with family history of mental illness are more prone to depression
- Students reporting suicidal thoughts have a significantly higher depression rate
- Depression is not evenly distributed across genders or satisfaction levels

---

## Potential Next Steps

- Build a classification model (e.g., Logistic Regression or Random Forest) to predict depression status
- Perform feature selection to optimize model performance
- Develop an interactive dashboard using Streamlit or Tableau
- Explore relationships between suicidal thoughts and other variables as a sub-analysis
- Apply clustering to segment students into different mental health risk profiles