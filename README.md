# 🚀 Project Title: Bridge Condition Regression

## 📌 Overview

Built a regression-based model to predict bridge condition ratings for the Texas Department of Transportation using predictors including age, average usage, truck traffic, material, and design.  
Performed feature engineering (e.g., deriving age), variable transformation, correlation analysis, and residual evaluation to assess model effectiveness and predictor impact.

---

## 🧠 Problem Statement

To understand how well the proposed variables can predict the condition of a bridge, and which variables have the greatest influence on it.

---

## 📊 Dataset

- **File:** `tx19_bridges_sample.csv`  
- **Source:** [National Bridge Inventory](https://www.fhwa.dot.gov/bridge/nbi/ascii.cfm)  
- **Columns:**
  - `Age`: Derived from `Year` (current year minus year built)
  - `AverageDaily`: Average daily traffic volume
  - `Trucks_percent`: Percent of traffic made up of trucks
  - `Material`: Primary bridge material
  - `Design`: Structural design of the bridge
  - `Current_Condition`: Derived by summing `Deck_rating`, `Superstr_rating`, and `Substr_rating`

---

## 📓 Notebook

👉 [`Bridge-condition-regression.ipynb`](Bridge-condition-regression.ipynb)

---

## ✨ Key Features

### 🔍 Section 1: Data Preparation

- Loaded and cleaned the dataset, removed null values and outliers
- Created the `Age` variable, renamed columns for clarity
- Explored data distributions with histograms and box plots
- Simplified categorical variables (`Material`, `Design`)
- Converted condition ratings (ordinal) into continuous scale
- Derived the target variable: `Current_Condition`

### 📊 Section 2: Exploratory Data Analysis

- Analyzed correlation matrix and visualized with heatmap
- Created scatter plots and pair plots for continuous variables
- Used kernel density plots to compare group distributions
- Performed crosstabs and normalization for categorical variables
- Plotted conditional probability distributions and heatmaps

### 🤖 Section 3: Regression Modeling

- Applied regression using both continuous and categorical predictors
- Evaluated model performance using **R² = 0.456**
- Analyzed residual distributions to assess model fit
- Compared coefficients and interpreted variable influence
- Summarized key insights and project conclusions

---

## 📈 Final Results & Conclusion

The regression model explains approximately **46%** of the variance in bridge condition (**R² = 0.456**).  
This shows that the selected variables can predict condition **fairly well**, though improvements are possible.

### 🔢 Regression Coefficients (Key Insights)

| Predictor           | Coefficient (β) | Interpretation                                       |
|---------------------|------------------|-------------------------------------------------------|
| Age                 | -0.0485          | Each 1-year increase reduces condition by ~4.8%       |
| Average Use         | -7.97×10⁻⁷       | Negligible effect                                     |
| Percent Trucks      | +0.0047          | Minimal impact                                        |
| Material: Other     | +0.3539          | 35% better than concrete                              |
| Material: Steel     | -1.376           | 1.3% worse than concrete                              |
| Material: Timber    | -3.197           | 3.3% worse than concrete                              |
| Design: Other       | +0.011           | Almost no difference from beam design                 |
| Design: Slab        | -0.082           | Slightly worse than beam design                       |

### 🧠 Key Observations

- **Age** is the most influential predictor — older bridges tend to be in worse condition.
- **Traffic volume** and **truck percentage** show minimal influence.
- **Material type** significantly impacts condition:
  - Timber and steel bridges are in worse condition than concrete ones.
- **Design type** contributes little to predictive power.

---

## 🎯 Overall Conclusion

- **Structural age** and **material** are the strongest predictors of bridge condition.
- While the model doesn't capture all variance, it provides actionable insights for **infrastructure risk assessment**.
- **Potential improvements:**
  - Include more variables (e.g., regional climate, maintenance history)
  - Try non-linear models (e.g., Random Forest, Gradient Boosting)
  - Segment analysis by region or bridge type

---

## 🛠️ Tools Used

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn
