# 🚗 Car Price Prediction with Machine Learning

This project implements machine learning regression models to predict the selling price of used cars based on floral/structural characteristics, historical usage, and metadata.

## 📊 Dataset Features

The dataset `car data.csv` contains 301 records with the following columns:
- `Selling_Price`: Price the owner wants to sell the car for (Target variable, in Lakhs).
- `Present_Price`: Showroom price of the new car (in Lakhs).
- `Driven_kms`: Total kilometers driven by the car.
- `Fuel_Type`: Fuel type (Petrol, Diesel, CNG).
- `Selling_type`: Seller type (Dealer, Individual).
- `Transmission`: Transmission type (Manual, Automatic).
- `Owner`: Number of previous owners (0, 1, 3).
- `Car_Age` *(Engineered)*: Age of the car relative to the newest car in the dataset (2018).

## ⚙️ Workflow & Preprocessing
1. **Feature Engineering:** Calculated the age of each car as `Car_Age = 2018 - Year` and dropped the original high-cardinality `Car_Name` and `Year` columns.
2. **Categorical Encoding:** One-hot encoded `Fuel_Type`, `Selling_type`, and `Transmission` (with `drop_first=True` to prevent multicollinearity).
3. **Data Splitting:** Partitioned the dataset into 80% training and 20% testing sets.
4. **Model Comparison:** Trained and compared four regression algorithms on the test set:
   - Linear Regression
   - Decision Tree Regressor
   - Random Forest Regressor
   - Gradient Boosting Regressor

## 🤖 Regression Model Comparison

| Regression Model | Test $R^2$ Score | MAE (Lakhs) | RMSE (Lakhs) |
| :--- | :--- | :--- | :--- |
| **Gradient Boosting** | **96.17%** | **0.59** | **0.94** |
| **Random Forest** | **95.95%** | **0.64** | **0.97** |
| **Decision Tree** | **94.55%** | **0.73** | **1.12** |
| **Linear Regression** | **84.89%** | **1.22** | **1.87** |

### Key Results
- **Best Model:** The **Gradient Boosting Regressor** achieved the highest $R^2$ score of **96.17%** on the test set, meaning it explains 96.17% of the variance in used car selling prices.
- **Top Features:** Showroom price (`Present_Price`) is the single most dominant predictor of used car pricing, followed by `Car_Age` and `Driven_kms`.

## 📈 Visualizations
The following plots are generated automatically by the notebook:
- [selling_price_distribution.png](selling_price_distribution.png): Distribution of selling prices.
- [price_relationship.png](price_relationship.png): Present Price vs Selling Price scatter plot.
- [feature_correlation_heatmap.png](feature_correlation_heatmap.png): Heatmap showing correlations between preprocessed variables.
- [model_r2_comparison.png](model_r2_comparison.png): Comparison of test $R^2$ scores.
- [actual_vs_predicted_selling_prices.png](actual_vs_predicted_selling_prices.png): Scatter plot of actual vs predicted prices for Gradient Boosting.
- [best_model_feature_importance.png](best_model_feature_importance.png): Relative feature importance for the best model.

## 🛠️ How to Run
1. Activate the Python virtual environment:
   ```bash
   # On Windows
   ..\venv\Scripts\activate
   ```
2. Run the notebook to train and evaluate:
   ```bash
   jupyter notebook car_price_prediction.ipynb
   ```
   Or execute it headlessly:
   ```bash
   jupyter nbconvert --to notebook --execute --inplace car_price_prediction.ipynb
   ```
