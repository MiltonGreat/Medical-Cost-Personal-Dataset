# Medical Cost Personal Dataset

## Overview

The dataset includes personal information such as age, sex, BMI, number of children, smoking status, and the region of residence, along with the corresponding medical insurance charges for each individual. The goal of this project is to explore how different factors (such as age, BMI, and smoking status) impact the medical insurance cost and to build a better understanding of the distribution of these expenses.

## Project Overview

The objective of this project is to:
- **Analyze the distribution of medical insurance costs**: Understanding how the charges vary with different factors.
- **Identify relationships between personal attributes**: Examining how age, BMI, smoking status, and other features influence medical insurance premiums.
- **Perform data cleaning and preprocessing**: Address missing values, outliers, and imbalanced classes for further analysis or modeling.

## Dataset

The dataset contains the following columns:

- **age**: The age of the individual.
- **sex**: The sex of the individual (male, female).
- **bmi**: The body mass index (BMI) of the individual.
- **children**: The number of children/dependents covered by the insurance.
- **smoker**: Whether the individual is a smoker (yes, no).
- **region**: The region in which the individual resides (southeast, southwest, northwest, northeast).
- **charges**: The medical insurance costs for the individual.

## Data Analysis & Preprocessing

### Steps Performed:
1. **Missing Data Handling**: 
   - The missing values in the `bmi` column were imputed using the median.
   - The missing values in the `smoker` column were imputed using the mode (most frequent value).

2. **Outlier Handling**: 
   - Outliers in the `charges` column were detected using the Interquartile Range (IQR) method and removed to ensure the integrity of the analysis.

3. **Log Transformation**: 
   - The `charges` column was log-transformed using the `np.log1p` function to reduce skewness and improve the distribution.

4. **One-Hot Encoding**: 
   - Categorical features (`smoker` and `region`) were encoded using one-hot encoding to convert them into numeric variables suitable for analysis.

5. **Class Imbalance Handling**:
   - The `smoker_yes` class (smoker vs. non-smoker) was imbalanced, with far more non-smokers than smokers. To address this, **undersampling** was performed to balance the dataset. After undersampling, the dataset contains 138 smokers and 138 non-smokers.

### Visualizations:
The following visualizations were created:
- **Distribution of Medical Charges**: A histogram with a KDE plot to visualize the distribution of insurance charges.
- **Pairplot**: A pairplot to visualize relationships between age, BMI, children, and charges, with different colors for `sex`.
- **Boxplots**: 
   - Boxplot to visualize the effect of smoking status on medical charges.
   - Boxplot to visualize the effect of region on medical charges.
- **Correlation Heatmap**: To check the correlations between numerical features like age, BMI, children, and charges.

### Key Insights

- **Charges**: The target variable is `charges`, representing the medical insurance cost for an individual. 
- **Smoker Impact**: Smoking status is expected to have a significant impact on insurance costs.
- **Age and BMI**: These factors are also anticipated to influence the medical charges.

## Source

https://www.kaggle.com/datasets/mirichoi0218/insurance
