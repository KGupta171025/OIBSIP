# 🌸 Iris Flower Classification

This project implements machine learning models to classify Iris flowers into three species (**Setosa, Versicolor, and Virginica**) based on sepal and petal measurements (length and width).

## 📊 Dataset Description

The Iris dataset contains 150 samples with 5 features:
1. `SepalLengthCm` (in cm)
2. `SepalWidthCm` (in cm)
3. `PetalLengthCm` (in cm)
4. `PetalWidthCm` (in cm)
5. `Species` (Target: `Iris-setosa`, `Iris-versicolor`, or `Iris-virginica`)

## 📈 Exploratory Data Analysis (EDA) Insights

Key observations from data visualizations:
- **Setosa is Linearly Separable:** The Setosa species has highly distinct petal dimensions (much shorter and narrower) and can be easily separated from Versicolor and Virginica using simple linear boundaries.
- **Petal Length & Width Correlation:** There is a very strong positive correlation (0.96) between Petal Length and Petal Width.
- **Versicolor & Virginica Overlap:** Versicolor and Virginica exhibit slight overlap in their sepal and petal distributions, making non-linear classifiers (like SVM) very suitable for the task.

The following visualizations were generated:
- [iris_pairplot.png](iris_pairplot.png): Pairwise features plotted by species.
- [iris_correlation.png](iris_correlation.png): Heatmap showing correlation between numerical features.
- [iris_boxplots.png](iris_boxplots.png): Feature distribution boxplots for each species.

## 🤖 Model Evaluation and Comparison

The dataset was split into 80% training and 20% testing sets (stratified to ensure equal class distributions). Features were standardized using a `StandardScaler`. Four different algorithms were evaluated:

| Machine Learning Model | Test Accuracy |
| :--- | :--- |
| **Support Vector Machine (SVM)** | **96.67%** |
| **Logistic Regression** | **93.33%** |
| **K-Nearest Neighbors (KNN)** | **93.33%** |
| **Random Forest** | **90.00%** |

### Key Results
- **Best Classifier:** The **Support Vector Machine (SVM)** model with an RBF kernel achieved the highest accuracy of **96.67%** on the test set.
- **Confusion Matrix:** The confusion matrix ([best_model_confusion_matrix.png](best_model_confusion_matrix.png)) shows that only 1 instance of `Iris-versicolor` was misclassified as `Iris-virginica`, while all other instances of Setosa, Versicolor, and Virginica were predicted correctly.

## 🛠️ How to Run

1. Activate the Python virtual environment:
   ```bash
   # On Windows
   ..\venv\Scripts\activate
   ```
2. Run the Jupyter Notebook to train and evaluate the models:
   ```bash
   jupyter notebook iris_classification.ipynb
   ```
   Or run it headlessly to update outputs:
   ```bash
   jupyter nbconvert --to notebook --execute --inplace iris_classification.ipynb
   ```
