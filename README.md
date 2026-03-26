# King County House Price Prediction

## Overview
Regression project predicting house sale prices in King County, USA
(May 2014 – May 2015). Built as part of my Specialist Diploma in
Data Science (AI) at Singapore Polytechnic.

**Best Model: Optimised Random Forest | RMSE: ~146,989 | R²: 0.85**

---

## Dataset
- Source: [Kaggle — House Sales in King County](https://www.kaggle.com/harlfoxem/housesalesprediction)
- 21,613 entries, 21 features
- No missing values

---

## Approach

### 1. Exploratory Data Analysis
- Summary statistics, data types, null value check
- Pairplot of key features vs price
- Correlation heatmap to identify multicollinearity

### 2. Feature Engineering
- Dropped `id` (non-informative) and `date` (difficult to quantify)
- Standardised all features using `StandardScaler`

### 3. Models Trained
| Model | RMSE | MAE |
|---|---|---|
| Linear Regression | 212,540 | 127,493 |
| Random Forest | 148,710 | 72,779 |
| Tuned Random Forest | 146,989 | — |

### 4. Hyperparameter Tuning
- GridSearchCV with 5-fold cross-validation
- Best parameters: `max_depth=20`, `min_samples_split=2`, `n_estimators=300`

### 5. Evaluation
- RMSE, MAE, R² score
- 5-fold cross-validated RMSE: ~126,578 (± 8,804)

---

## Key Findings
- **sqft_living** was the strongest predictor of house price
- **grade** and **lat** (latitude/location) were also highly important
- `view` had lower importance than expected compared to Singapore's market

---

## Files
| File | Description |
|---|---|
| `King_County_House_Sales_THR.ipynb` | Full notebook with analysis and model pipeline |
| `kc_house_data.csv` | King County house sales dataset |

---

## Tools & Libraries
- Python, Pandas, NumPy
- scikit-learn (LinearRegression, RandomForestRegressor, GridSearchCV)
- Matplotlib, Seaborn

---

## Author
**Tan Han Rong**
Specialist Diploma in Data Science (AI), Singapore Polytechnic
