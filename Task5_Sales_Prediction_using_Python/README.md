# ✉️ Sales Prediction using Python

This project builds machine learning regression models to predict sales product transactions based on the advertising budgets spent on three mediums: **TV, Radio, and Newspaper**.

## 📊 Dataset Features

The dataset `Advertising.csv` contains 200 samples with the following variables:
- `TV`: Advertising budget spent on TV (in thousands of dollars).
- `Radio`: Advertising budget spent on Radio (in thousands of dollars).
- `Newspaper`: Advertising budget spent on Newspaper (in thousands of dollars).
- `Sales` *(Target Variable)*: Sales of the product (in thousands of units).

## ⚙️ Workflow & Preprocessing
1. **Data Cleaning:** Dropped the redundant index column `Unnamed: 0` and checked for missing values.
2. **Exploratory Analysis:** Plotted distributions and relationship trend lines for each advertising medium against sales.
3. **Data Splitting:** Partitioned the dataset into 80% training and 20% testing sets.
4. **Model Comparison:** Trained and compared four regression models on the test set:
   - Linear Regression
   - Decision Tree Regressor
   - Random Forest Regressor
   - Gradient Boosting Regressor

## 🤖 Regression Model Comparison

| Regression Model | Test $R^2$ Score | MAE | RMSE |
| :--- | :--- | :--- | :--- |
| **Gradient Boosting** | **98.31%** | **0.62** | **0.73** |
| **Random Forest** | **98.13%** | **0.62** | **0.77** |
| **Decision Tree** | **93.11%** | **0.99** | **1.47** |
| **Linear Regression** | **89.94%** | **1.46** | **1.78** |

### Key Results
- **Best Model:** The **Gradient Boosting Regressor** achieved the highest $R^2$ score of **98.31%** on the test set, explaining almost all variance in product sales.
- **Top Channels:** TV spend is the most dominant factor in sales volume, followed by Radio spend. Newspaper spend shows weak correlation and low importance in predictions.

## 📈 Visualizations
The following plots are generated automatically by the notebook:
- [sales_distribution.png](sales_distribution.png): Distribution of sales.
- [sales_vs_budgets.png](sales_vs_budgets.png): Scatter plots with regression lines for TV, Radio, and Newspaper spends vs Sales.
- [sales_correlation_heatmap.png](sales_correlation_heatmap.png): Heatmap showing correlations between features.
- [model_r2_comparison.png](model_r2_comparison.png): Comparison of test $R^2$ scores.
- [actual_vs_predicted_sales.png](actual_vs_predicted_sales.png): Scatter plot of actual vs predicted sales for Gradient Boosting.
- [best_model_feature_importance.png](best_model_feature_importance.png): Relative feature importance for the best model.

## 🛠️ How to Run
1. Activate the Python virtual environment:
   ```bash
   # On Windows
   ..\venv\Scripts\activate
   ```
2. Run the notebook to train and evaluate:
   ```bash
   jupyter notebook sales_prediction.ipynb
   ```
   Or execute it headlessly:
   ```bash
   jupyter nbconvert --to notebook --execute --inplace sales_prediction.ipynb
   ```
