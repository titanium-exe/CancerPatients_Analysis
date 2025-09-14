
# Cancer Patients Analysis

This project focuses on a comprehensive analysis of a global cancer patient dataset from 2015 to 2024. The aim is to understand cancer severity, identify key risk factors, evaluate survival trends, assess economic burden, and explore the effectiveness of treatment across different demographics and cancer types.

## Table of Contents

- [Dataset](#dataset)
- [Objectives](#objectives)
- [Technologies Used](#technologies-used)
- [Data Overview](#data-overview)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Predictive Modeling](#predictive-modeling)
- [Statistical Testing](#statistical-testing)
- [Key Findings](#key-findings)
- [Conclusion](#conclusion)

## Dataset

- **File**: `global_cancer_patients_2015_2024.csv`
- **Source**: Mounted from Google Drive via Google Colab
- **Features include**:
  - Demographics: Age, Gender, Country_Region
  - Cancer-specific: Cancer_Type, Cancer_Stage
  - Risk Factors: Air Pollution, Alcohol Use, Smoking, Genetic Risk, Obesity Level
  - Outcomes: Target Severity Score, Survival Years, Treatment Cost (USD)

## Objectives

1. Perform descriptive statistics and visualizations for key demographic and clinical features.
2. Analyze distribution and severity of cancer types and stages.
3. Identify key risk factors influencing cancer severity and survival.
4. Explore country-wise and age-wise treatment costs.
5. Examine statistical relationships between treatment cost and survival.
6. Evaluate the significance of interaction effects among variables.
7. Apply machine learning (Random Forest) for feature importance analysis.

## Technologies Used

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- Scikit-learn
- Statsmodels
- SciPy

## Data Overview

- Total number of patients: ~50,000+
- Age distribution: Broad, allowing age-based comparative analysis
- Gender: Almost equal distribution
- Cancer Types: 8 major categories including Breast, Lung, Colon, Liver, Leukemia, etc.
- Cancer Stages: 5 stages, evenly distributed
- Treatment Cost: Ranges from $5,000 to $100,000
- Risk Factors: Standardized scores for environmental and lifestyle variables

## Exploratory Data Analysis

### 1. Age & Gender Distribution
- Age distribution is even across young and elderly.
- Gender distribution is balanced, allowing comparative analysis.

### 2. Cancer Type & Stage
- Colon and Prostate cancers are most common.
- Most stages (0 to IV) are equally represented.

### 3. Country Representation
- Patients from 10 countries; Australia is the most represented.
- Enables meaningful cross-country comparisons.

### 4. Risk Factors Summary
- Smoking, Genetic Risk, and Alcohol Use showed the highest average values.
- All risk factors were standardized and suitable for modeling.

## Predictive Modeling

### 1. Correlation Analysis
- **Severity Score**:
  - Strongest positive correlation with Smoking, Genetic Risk, and Alcohol Use.
  - Weak correlation with Age.
- **Survival Years**:
  - Very weak or no correlation with any selected features.

### 2. Random Forest Regression
- **Severity Score**:
  - Random Forest model achieved moderate R² with minor overfitting.
  - Most important features: Smoking, Genetic Risk, Air Pollution.
- **Survival Years**:
  - Very low R² even after hyperparameter tuning.
  - Indicates need for more clinical variables (e.g., treatment type).

## Statistical Testing

### 1. Treatment Cost vs Survival Years
- Pearson and Spearman correlation tests failed to reject the null hypothesis.
- No significant relationship found.

### 2. Cancer Stage vs Cost & Survival
- Kruskal-Wallis test (non-parametric ANOVA alternative) used due to non-normality.
- No significant differences found in average cost or survival across stages.

### 3. Interaction Effect: Smoking & Genetic Risk
- Regression analysis with interaction term:
  - No statistically significant interaction found between Smoking and Genetic Risk on cancer severity.

## Key Findings

- 38-40% of all cancer cases are diagnosed at early stages (Stage 0 or I).
- Risk Factors do not explain variation in survival years effectively.
- Treatment cost does not correlate with survival outcomes.
- There is no significant interaction between smoking and genetic risk on severity.

## Conclusion

This analysis offers insights into the global burden of cancer, the role of risk factors, and healthcare costs across countries and demographics. While severity can be partially explained by lifestyle and genetic risk factors, survival prediction requires additional variables. The project demonstrates the importance of both statistical and machine learning approaches in healthcare data analysis.
