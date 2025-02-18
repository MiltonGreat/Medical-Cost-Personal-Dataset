# Medical Cost Personal Dataset

## Overview

This project involves the analysis and prediction of medical insurance charges based on personal attributes such as age, sex, BMI, number of children, smoking status, region of residence, and other factors. The goal is to explore how these factors impact medical expenses, understand the distribution of charges, and build a regression model to predict medical insurance costs.

## Project Overview

The objective of this project is to:
- **Analyze the distribution of medical insurance costs**: Understanding how the charges vary with different factors.
- **Identify relationships between personal attributes**: Examining how age, BMI, smoking status, and other features influence medical insurance premiums.
- **Perform data cleaning and preprocessing**: Address missing values, outliers, and imbalanced classes for further analysis or modeling.
- **Modeling and Evaluation**: Build regression models to predict medical charges and evaluate their performance.

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

### Modeling:

1. **Best Model**: The Polynomial Regression model yielded the best performance, with the lowest MAE, MSE, and RMSE, and the highest R² score. It was able to capture the non-linear relationships in the data effectively.
2. **Runner-up**: The Random Forest Regressor performed well as a robust alternative, producing competitive metrics across MAE, MSE, and R², and was fine-tuned for optimal performance.
3. **Underperformer**: The Decision Tree Regressor underperformed, with higher MAE, MSE, RMSE, and a lower R² score, suggesting overfitting and poor generalization.

### Hyperparameter Tuning:

Random Forest Regressor was fine-tuned through cross-validation, testing 27 different hyperparameter combinations. This tuning led to better generalization, reducing error metrics and improving the model's ability to explain the variance in charges.

### Visualizations:
The following visualizations were created:
- **Distribution of Medical Charges**: A histogram with a KDE plot to visualize the distribution of insurance charges.
- **Pairplot**: A pairplot to visualize relationships between age, BMI, children, and charges, with different colors for `sex`.
- **Boxplots**: 
   - Boxplot to visualize the effect of smoking status on medical charges.
   - Boxplot to visualize the effect of region on medical charges.
- **Correlation Heatmap**: To check the correlations between numerical features like age, BMI, children, and charges.

### Key Insights

- **Charges**: The target variable, charges, represents the medical insurance costs for an individual, and its wide range indicates that multiple factors contribute to medical expenses.
- **Smoker Impact**: Smoking status is the most significant predictor of medical expenses, with smokers tending to have much higher charges.
- **Age and BMI**: Both age and BMI show a positive relationship with medical charges. Older individuals and those with higher BMI values tend to have higher medical expenses, though BMI is not as dominant as smoking.
- **Children**: The number of children does not have a strong correlation with medical charges in this dataset, indicating that family-related health conditions or coverage may not be a major factor.
- **Sex and Region**: These factors show weak correlations with medical charges, suggesting they are less influential in predicting insurance costs.

### Source

Dataset: [Medical Cost Dataset on Kaggle](https://www.kaggle.com/datasets/mirichoi0218/insurance)
