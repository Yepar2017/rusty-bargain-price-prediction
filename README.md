# Used Car Price Prediction — Rusty Bargain

## Business Problem

Rusty Bargain is a used car dealership that wants to estimate vehicle prices based on technical and market characteristics.  
Accurate price estimation is critical for maintaining competitiveness while maximizing profit margins.

The goal of this project is to build a regression model capable of predicting used car prices using historical listing data.

---

## Dataset Overview

The dataset contains vehicle listings with features such as:

- Model year
- Odometer (mileage)
- Engine cylinders
- Fuel type
- Transmission
- Vehicle type
- Condition
- Days listed
- Posting date
- And other categorical attributes

Target variable:
- `price`

---

## Data Preparation

- Missing values handled using median imputation (numerical features)
- Categorical missing values filled with `"unknown"`
- Binary variables normalized
- One-Hot Encoding applied to categorical features
- Data split into training and testing sets (75% / 25%)

---

## Modeling Approach

The following models were evaluated using RMSE:

1. Linear Regression (baseline)
2. Random Forest
3. Gradient Boosting (sklearn)
4. LightGBM

Cross-validation (5-fold) was performed for the final model to ensure stable performance.

---

## Model Performance

| Model | RMSE |
|-------|------|
| Linear Regression | ~7,447 |
| Random Forest | ~5,593 |
| Gradient Boosting (sklearn) | ~5,973 |
| **LightGBM** | **~5,421** |

Cross-Validation RMSE (LightGBM): **~5,311**

The close alignment between test and cross-validation results indicates strong generalization performance.

---

## Feature Importance Insights

After grouping one-hot encoded features, the most influential factors in price prediction were:

1. Vehicle model
2. Model year
3. Odometer (mileage)
4. Engine cylinders
5. Vehicle condition
6. Vehicle type

These findings align with real-world pricing logic, where vehicle age, mileage, and specific model demand heavily influence price.

---

## Business Impact

The final LightGBM model provides accurate and stable vehicle price predictions.  
This can help the dealership:

- Improve pricing consistency
- Reduce underpricing or overpricing risk
- Respond more quickly to market conditions
- Enhance overall competitiveness

---

## Technologies Used

- Python
- Pandas
- Scikit-learn
- LightGBM
- Matplotlib / Seaborn

---

## Final Note

This project demonstrates a complete machine learning workflow:

- Business understanding
- Data cleaning
- Exploratory data analysis
- Model comparison
- Cross-validation
- Interpretability through feature importance
- Business-oriented conclusions
