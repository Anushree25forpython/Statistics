
# 🚀 Project Title - Bridge regression

## 📌 Overview
Built a regression-based model to predict bridge condition ratings for the Texas Department of Transportation using predictors including age, average usage, truck traffic, material and design. 
Performed feature engineering (e.g. deriving age), variable transformation, correlation, and residual evaluation to assess model effectiveness and predictor impact.

## 🧠 Problem Statement
To investigate/understand how well the proposed variables can predict the bridge condition and which of the proposed variables has more influence on the current condition.

## 📊 Dataset
- File: `tx19_bridges_sample.csv`
- Source: [National Bridge Inspection] (https://www.fhwa.dot.gov/bridge/nbi/ascii.cfm)
- Columns: Age (derived from variable Year - The year the bridge was built subtrcating the current year), AverageDaily - the average daily traffic (number of vehicles), Trucks_percent - The percent of traffic made up of 'trucks' (i.e. lorries), Material - The dominant material the bridge is made from, variable Design - The design of the bridge, current condition - derived from variables Deck_rating (condition of the deck of the bridge), Superstr_rating (condition of the bridge superstructure) and Substr_rating (condition of the bridge substructure (foundations)).

## 📓 Notebook
Link to your notebook: [`Bridge_Regression.ipynb`](Bridge_Regression.ipynb)

## ✨ Key Features

- 🔍 **Section 1: Data Preparation**
  - Sourced from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)
  - Loaded and cleaned the dataset, removed null values and outliers
  - Created a predictor variable `Age` from year, and renamed variables for clarity
  - Explored data distributions (histograms, box plots)
  - Simplified categorical variables (material, design)
  - Converted condition ratings (ordinal) into continuous scale
  - Derived the target variable: current bridge condition

- 📊 **Section 2: Exploratory Data Analysis**
  - Analyzed correlation matrix and visualized heatmap
  - Created scatter plots and pair plots for continuous variables
  - Used kernel density plots to compare group distributions
  - Performed crosstabs and normalization for categorical variables
  - Plotted conditional probability distributions and heatmaps

- 🤖 **Section 3: Regression Modeling**
  - Applied regression using both continuous and categorical predictors
  - Evaluated model performance using R² (coefficient of determination)
  - Analyzed residual distributions to assess model fit
  - Compared predictor coefficients and interpreted results
  - Summarized key insights and project conclusions

- ✅ Final results & metrics

## 🎯 Results & Conclusion
The proposed variables can predict the bridge condition fairly well approximately close to 50% .

To be precise R2 being 0.456, proportion of the variance is 46% for dependent variable i.e the bridge condition which is predicted by the independent variables in the regression model

From the comparison of coefficients we conclude that the proposed variable Age has the maximum influence on the target variable when compared to other predictors with a value of 64 versus 7.8 for percent trucks predictor variable.
