# IMDB_MovieReviews_SentimentAnalysis

### Objective 🎯
Sentiment analysis is a powerful tool in Natural Language Processing (NLP) that helps determine the sentiment behind a piece of text. This project aims to classify movie reviews as either **positive** or **negative** by leveraging different machine learning models. The analysis involves ***text preprocessing, data vectorization (using TF-IDF), model training, evaluation, and performance comparison*** across multiple models, including **Naive Bayes, Logistic Regression**, and **DistilBERT**.

### 1. Basic Text Statistics 📊

Before diving into preprocessing, I extracted basic text statistics:

* **Word Count**: Counted the number of words per review to analyze length distribution.
* **Sentence Length**: Measured sentence complexity within reviews.



### 2. Review Column Preprocessing Pipeline 🔧
So since the dataset has 2 columns: 'review' and 'sentiment' (positive/negative), I just needed to work on the 'review' column.
Here's a breakdown of our preprocessing pipeline:

**1. Converting to Lowercase**: 📝 This ensures uniformity, so words like "Great" and "great" are treated the same.
**2. Removing Special Characters, Punctuation, and Numbers:** 🚫 Eliminates noise from the text. Numbers and symbols (like "$") do not typically add value to sentiment analysis.
**3. Tokenizing**: ✂️ Tokenization splits text into individual words (tokens), enabling the model to process and understand them.
**4. Removing Stopwords**: 🧹 Removed common words like "the" and "is" that don’t contribute much meaning.
**5. Lemmatizing**: 🔄 – Converted words to their base form (e.g., "running" → "run").

### 3. Data Vectorization using TF-IDF 🔢
To transform the text data into numerical form, I use TF-IDF (Term Frequency-Inverse Document Frequency). This method weighs the importance of words in each review based on their frequency and significance in the entire dataset.

* **Stopwords Removal**: Continuing to remove common stopwords from the text to reduce noise.
* **Max Features**: Retains the top 5,000 most informative words
This step converts each review into a sparse matrix that can be fed into machine learning models.


### 4. End-to-End Model Training, Evaluation, and Timing 🤖
Once the data is preprocessed and vectorized, we train three models:

* **Naive Bayes**: ⚡ A probabilistic classifier based on word frequency.
* **Logistic Regression**:🏆  A linear model optimized for binary classification.
* **DistilBERT**: 🤖 A transformer-based model, which is pre-trained on a large corpus of data and fine-tuned for sentiment analysis.

### 5. Evaluation and Timing ⏳
I evaluate each model based on several performance metrics: **Accuracy, Precision, Recall,** and **F1-Score.** 


| Model                | Accuracy  | Precision | Recall   | F1-Score | Runtime |
| ---------------------| ----------| ----------| ---------| ---------| --------|
| 🏆 Naive Bayes       | 0.8505    | 0.850336 | 0.8535    | 0.8519   | 0.00    |
|⚡ Logistic Regression | 0.8880    | 0.8762    | 0.9057   | 0.8907   | 0.01    |
| 🤖 DistilBERT        | 0.8882    | 0.9147    | 0.8581   | 0.8855   | 97.70   |
| ---------------------| ----------| ----------| ---------| ---------| --------|



Model	Accuracy	Precision	Recall	F1-Score	Runtime (min)
0	Naive Bayes (5K)	0.8505	0.850336	0.853542	0.851936	0.00
1	Logistic Regression (5K)	0.8880	0.876176	0.905735	0.890710	0.01
2	DistilBERT (5K)	0.8882	0.914745	0.858107	0.885521	97.70


