# 📈 Unemployment Analysis with Python

This project analyzes the unemployment rate in India, focusing on monthly trends, regional variances, and the significant impact of the **COVID-19 pandemic and subsequent lockdown in 2020**.

## 📊 Datasets Used

Two CSV files are used for a comprehensive analysis:
1. **`Unemployment in India.csv`**: Segregates data into Rural and Urban areas.
2. **`Unemployment_Rate_upto_11_2020.csv`**: Provides regional coordinates (longitude and latitude) and categorizes states into geographical divisions (North, South, East, West, Northeast).

## 📈 Key Insights

### 1. COVID-19 Lockdown Impact (2020)
The national lockdown declared on **March 24, 2020**, triggered a severe spike in unemployment:
- **Pre-Lockdown Average (Jan - Mar 2020):** **9.76%**
- **Lockdown Peak Average (Apr - Jul 2020):** **16.50%**
- **Post-Lockdown Recovery (Aug - Oct 2020):** **9.02%**

### 2. Worst-Hit States (Increase during Lockdown Peak)
The states with the largest increase in unemployment rates comparing the lockdown peak to pre-lockdown levels were:
1. **Puducherry:** Increase of **+37.26%**
2. **Jharkhand:** Increase of **+23.50%**
3. **Tamil Nadu:** Increase of **+22.15%**
4. **Bihar:** Increase of **+18.69%**
5. **Karnataka:** Increase of **+12.26%**

### 3. Rural vs. Urban Differences
Urban areas experienced higher and more volatile unemployment compared to rural areas:
- **Rural Unemployment Rate:** Mean of **10.32%** (range: 0.0% to 74.51%)
- **Urban Unemployment Rate:** Mean of **13.17%** (range: 0.0% to 76.74%)

## 📊 Visualizations Generated

The analysis outputs the following plots:
- `average_unemployment_by_state.png`: State-wise average unemployment rate.
- `labor_metrics_correlation.png`: Correlation matrix of unemployment rate, employed population, and participation rate.
- `rural_vs_urban_unemployment.png`: Boxplot showing Rural vs. Urban unemployment distributions.
- `unemployment_by_division.png`: Average unemployment by geographical division.
- `lockdown_period_comparison.png`: Comparison of average unemployment rate across periods.
- `unemployment_timeline_2020.png`: Line plot tracing monthly unemployment trends with a COVID-19 timeline indicator.
- `state_unemployment_increase_lockdown.png`: States ranked by increase in unemployment during the lockdown peak.

## 🛠️ How to Run

1. Activate the Python virtual environment:
   ```bash
   # On Windows
   ..\venv\Scripts\activate
   ```
2. Run the notebook:
   ```bash
   jupyter notebook unemployment_analysis.ipynb
   ```
   Or execute the notebook headlessly:
   ```bash
   jupyter nbconvert --to notebook --execute --inplace unemployment_analysis.ipynb
   ```
