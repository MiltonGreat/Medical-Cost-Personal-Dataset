# Medical Cost Personal Dataset

## Overview

The dataset includes personal information such as age, sex, BMI, number of children, smoking status, and the region of residence, along with the corresponding medical insurance charges for each individual. The goal of this project is to explore how different factors (such as age, BMI, and smoking status) impact the medical insurance cost and to build a better understanding of the distribution of these expenses.

This dataset provides a valuable opportunity to apply data analysis and machine learning techniques such as exploratory data analysis (EDA), data visualization, and correlation analysis.

### Quality Issues:

- Missing demographic or health information (e.g., BMI or smoking status).
- Outliers in medical costs for extreme cases (e.g., catastrophic health events).
- Imbalanced data: higher representation of non-smokers or certain age groups.

Cleaning/Transformation:
- Impute missing values using median (e.g., for BMI) or mode (e.g., for smoking status).
- Log-transform medical costs to reduce skewness in the distribution.
- Encode categorical variables like "smoking status" using one-hot encoding.

Known Limitations:
- Does not include medical history, which might influence costs significantly.
- Potential regional or socioeconomic biases in the dataset.
- Data might not reflect costs for individuals without insurance.

## Dataset

The dataset contains the following columns:

- **age**: The age of the individual.
- **sex**: The sex of the individual (male, female).
- **bmi**: The body mass index (BMI) of the individual.
- **children**: The number of children/dependents covered by the insurance.
- **smoker**: Whether the individual is a smoker (yes, no).
- **region**: The region in which the individual resides (southeast, southwest, northwest, northeast).
- **charges**: The medical insurance costs for the individual.

### Key Insights

- **Charges**: The target variable is `charges`, representing the medical insurance cost for an individual. 
- **Smoker Impact**: Smoking status is expected to have a significant impact on insurance costs.
- **Age and BMI**: These factors are also anticipated to influence the medical charges.

## Project Goals

1. **Exploratory Data Analysis (EDA)**: 
   - Inspect the data for missing values, summary statistics, and distribution of variables.
   - Analyze the relationships between different variables (e.g., `age`, `bmi`, `smoker`, `charges`).

2. **Data Visualization**: 
   - Visualize the distribution of `charges`.
   - Examine how categorical variables like `smoker` and `region` impact the distribution of medical insurance costs.
   - Generate a correlation matrix to explore numerical variables and their relationships with insurance charges.

3. **Insights and Findings**: 
   - Identify factors most correlated with high medical insurance charges.
   - Discuss trends and patterns in the data.

## Source

https://www.kaggle.com/datasets/mirichoi0218/insurance
