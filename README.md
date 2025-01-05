# Driving Precision: Predicting Vehicle Weight with Linear Regression


## Overview

This project aims to build a predictive model for estimating a vehicle's curb weight using key features derived from exploratory data analysis (EDA). Accurate prediction of curb weight is crucial for manufacturers and analysts in vehicle design, safety compliance, and performance optimization.


## Business Case

The curb weight of a vehicle significantly impacts fuel efficiency, handling, and safety compliance. Accurate weight predictions allow:

- **Automotive manufacturers** to optimize design and production.
- **Performance analysts** to simulate real-world scenarios.
- **Safety engineers** to ensure vehicles meet regulatory standards.

This project focuses on constructing and evaluating regression models to predict curb weight, helping stakeholders make informed design and manufacturing decisions.


## Key Steps

### 1. Data Understanding & Preprocessing

- **Objective:** Ensure the dataset is clean, complete, and ready for analysis.
- **Actions Taken:**
  - Identified missing values and replaced placeholders (e.g., '?') with `NaN`.
  - Used **mean imputation** to fill missing values during model training.
  - Split data into predictors (`X`) and the target variable (`curb_weight`).

---

### 2. Exploratory Data Analysis (EDA)

- **Objective:** Understand relationships between features and the target variable.
- **Key Insights:**
  - Strong positive correlations identified between `engine_size`, `horsepower`, and `width` with `curb_weight`.
  - Visualization techniques like pairplots and boxplots helped uncover trends and potential outliers.

---

### 3. Feature Selection

- Based on EDA findings, selected two sets of features for regression models:
  - **Model 1:** `width`, `length`, `engine_size`
  - **Model 2:** `wheel_base`, `horsepower`, `city_mpg`

---

### 4. Model Construction

- Built linear regression models using `scikit-learn`, employing a pipeline with:
  - **SimpleImputer** for handling missing values.
  - **LinearRegression** for predictive modeling.

---

### 5. Model Evaluation

- Used **5-fold cross-validation** to ensure robust model performance evaluation.
- Metrics:
  - **R² Score:** Measures the proportion of variance explained by the model.
  - Calculated the average R² score across folds for each model.

---

### 6. Results & Selection

- **Model 1** demonstrated a superior average R² score (0.893) compared to Model 2, making it the preferred choice.
- Features `engine_size`, `horsepower`, and `width` were determined to be the most reliable predictors.

---

## Business Recommendations

1. **Adopt Model 1** for predicting curb weight as it offers high accuracy and uses explainable variables with strong business relevance.
2. **Monitor and Refine:** Conduct regular model updates with new data to maintain performance and adapt to changes in vehicle design trends.
3. **Outlier Investigation:** Examine the outliers observed in EDA to further improve model reliability.
4. **Advanced Techniques:** Explore non-linear models (e.g., Random Forest or Polynomial Regression) for potential performance gains.

---

## Next Steps

1. **Residual Analysis:** Verify assumptions of linear regression and assess areas for improvement.
2. **Feature Engineering:** Introduce interaction terms or polynomial features to capture non-linear relationships.
3. **Deployment:** Build an interactive dashboard for business stakeholders to input variables and obtain curb weight predictions.

---

## Project Structure

```
Driving-Precision/
│
├── data/
│   └── dataset.csv                # Dataset used for the project
├── notebooks/
│   ├── eda.ipynb                  # Exploratory Data Analysis notebook
│   ├── model_construction.ipynb   # Regression model construction and evaluation
├── src/
│   ├── preprocess.py              # Data preprocessing scripts
│   ├── train_model.py             # Model training pipeline
├── outputs/
│   ├── r2_scores.csv              # R² scores from cross-validation
│   └── model_1_summary.txt        # Model 1 performance summary
├── README.md                      # Project documentation
└── requirements.txt               # Python dependencies
```

---

## Requirements

- Python 3.8+
- Libraries:
  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `matplotlib`
  - `seaborn`

---
