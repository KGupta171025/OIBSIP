# Email Spam Detection

## What is Spam Detection?
We’ve all been the recipient of spam emails before. Spam mail, or junk mail, is a type of email that is sent to a massive number of users at one time, frequently containing cryptic messages, scams, or most dangerously, phishing content.

In this Project, use Python to build an email spam detector. Then, use machine learning to train the spam detector to recognize and classify emails into spam and non-spam. Let’s get started!

## Dataset Used
The dataset used for this project is `dataset.csv`, which contains two main columns:
- `v1`: The label indicating whether the message is `ham` (legitimate) or `spam`.
- `v2`: The raw text content of the email/message.

## Steps Followed
1. **Import Libraries**: Loaded essential libraries including `pandas`, `numpy`, and `sklearn`.
2. **Load Data**: Read the dataset using `pandas` and renamed the important columns to `label` and `message`.
3. **Data Cleaning**: Applied text preprocessing by converting text to lowercase, removing all punctuation, and filtering out English stopwords to retain only meaningful words.
4. **Convert Text \u2192 Numbers**: Utilized `TfidfVectorizer` (Term Frequency-Inverse Document Frequency) to transform the textual data into numerical feature vectors that the machine learning model can understand.
5. **Train Model**: Split the data into training and testing sets (80% / 20%) and trained a **Naive Bayes** model (`MultinomialNB`), which is highly effective and widely used for text classification tasks like spam detection.
6. **Evaluate & Show Output**: Evaluated the model's performance on the test set using accuracy score and confusion matrix. Demonstrated the model's practical usage by passing new example sentences and printing out their predictions.

## Result
The Naive Bayes model achieved an impressive accuracy of **96.77%** on the test set.
