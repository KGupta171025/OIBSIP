# ✉️ Email Spam Detection

This project implements machine learning models to classify email and SMS messages into **Spam** or **Ham** (legitimate).

## 📊 Dataset Used
The dataset used is `dataset.csv`, which contains two main columns:
- `v1`: The label indicating whether the message is `ham` (legitimate) or `spam`.
- `v2`: The raw text content of the message.

## ⚙️ Steps Followed
1. **Load and Clean Data**: Read the dataset using `pandas`, dropped unused columns, and cleaned the message text (lower-casing, removing punctuation, and filtering out English stopwords).
2. **Handle Class Imbalance**: Used stratified splitting (80% training / 20% testing) to maintain the proportion of spam/ham messages in both sets.
3. **Convert Text to Features**: Employed `TfidfVectorizer` to transform cleaned text into numerical TF-IDF feature vectors.
4. **Train and Compare Models**: Trained and compared four different classification algorithms with balanced class weights:
   - Naive Bayes (`MultinomialNB`)
   - Logistic Regression
   - Linear SVM (`LinearSVC`)
   - Random Forest Classifier
5. **Evaluate**: Analyzed accuracy scores, confusion matrices, and classification reports (precision, recall, and F1-score) to find the best model. Tested predictions using tricky phishing examples.

## 🤖 Model Comparison

| Machine Learning Model | Test Accuracy | Spam Recall |
| :--- | :--- | :--- |
| **Linear SVM** | **97.94%** | **90.67%** |
| **Logistic Regression** | **97.04%** | **88.67%** |
| **Naive Bayes** | **96.77%** | **76.00%** |
| **Random Forest** | **96.68%** | **75.33%** |

### Key Results
- **Best Classifier:** The **Linear SVM** model achieved the highest test accuracy of **97.94%** and a much higher recall for Spam (**90.67%**) compared to Naive Bayes (**76.00%**).
- **Phishing Detection:** Linear SVM successfully classifies tricky phishing messages like `"URGENT: Your account has been compromised. Update your details immediately."` as **Spam**, whereas the standard Naive Bayes classifier misclassifies it as Ham (Not Spam).
- **Confusion Matrix:** The confusion matrix ([best_model_confusion_matrix.png](best_model_confusion_matrix.png)) shows minimal classification errors for the test set.

## 📈 Visualizations
The following plots are generated automatically by the notebook:
- [spam_vs_not_spam.png](spam_vs_not_spam.png): Dataset class distribution.
- [model_accuracy_comparison.png](model_accuracy_comparison.png): Bar chart comparing the accuracies of all four models.
- [best_model_confusion_matrix.png](best_model_confusion_matrix.png): Confusion matrix of the best model (Linear SVM).

## 🛠️ How to Run
1. Activate the Python virtual environment:
   ```bash
   # On Windows
   ..\venv\Scripts\activate
   ```
2. Run the notebook to train and evaluate:
   ```bash
   jupyter notebook spam_detection.ipynb
   ```
   Or run it headlessly:
   ```bash
   jupyter nbconvert --to notebook --execute --inplace spam_detection.ipynb
   ```
