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




📊 Model Performance Breakdown

* **Naive Bayes** performed decently with **85.05% accuracy**, making it a fast and efficient model for large-scale text classification.

* **Logistic Regression** achieved **88.80% accuracy**, proving to be a strong baseline model with a balance between speed and accuracy.

* **DistilBERT** slightly outperformed Logistic Regression with **88.82% accuracy**, but at the cost of a significantly higher runtime **(~98 minutes)**.

### 6. Summary & Suggestions 📌

✅ **Best Trade-off**: Logistic Regression provides a great balance between speed and performance, making it ideal for large datasets with limited computational resources.

✅ **High-Accuracy Model**: DistilBERT delivers state-of-the-art performance but requires significant processing time, making it better suited for small-scale, high-quality analyses.

✅ **Fastest Model**: Naive Bayes is the best option for quick predictions on large datasets with only a slight dip in accuracy.

🚀 Future Improvements:

* **Hyperparameter tuning** to optimize each model further.

* **Experimenting with larger sample sizes** for better generalization.

* **Exploring other transformer models** like BERT or RoBERTa for higher accuracy.

This project highlights the trade-offs between **speed and accuracy** in sentiment analysis, showcasing how different models perform under real-world constraints. 🎥📊

If you want to connect with me, send me a "Hi 👋 " on LinkedIn [![text](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tatevik-khachatryan-/)


