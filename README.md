# IMDB_MovieReviews_SentimentAnalysis

### Objective 🎯
In this project, I aim to build a sentiment analysis model to classify movie reviews as either positive or negative. The goal is to compare different machine learning models, including **Naive Bayes, Logistic Regression,** and **DistilBERT**, to evaluate their performance in terms of ***accuracy, precision, recall***, and ***F1-score***.

I’ll also explore data preprocessing, feature extraction using **TF-IDF**, and evaluate the runtime of each model. The project is designed to provide insights into how traditional machine learning models compare with transformer-based models in terms of performance and computational efficiency.

### 1. Review Column Preprocessing Pipeline 🔧
So since the dataset has 2 columns: 'review' and 'sentiment' (positive/negative), I just needed to work on the 'review' column.
Here's a breakdown of our preprocessing pipeline:

**1. Converting to Lowercase**: This ensures uniformity, so words like "Great" and "great" are treated the same.
**2. Removing Special Characters, Punctuation, and Numbers:** This helps eliminate noise from the text. Numbers and symbols (like "$") do not typically add value to sentiment analysis.
**3. Tokenizing**: Tokenization splits text into individual words (tokens), enabling the model to process and understand them.
**4. Removing Stopwords**: Common words such as "the", "a", and "in" are removed as they don't contribute meaningful information for sentiment classification.
**5. Lemmatizing**: Words are reduced to their base forms (e.g., "running" becomes "run"), ensuring the model captures the semantic meaning of words better.

### 2. Data Vectorization using TF-IDF 💻
To transform the text data into numerical form, I use TF-IDF (Term Frequency-Inverse Document Frequency). This method weighs the importance of words in each review based on their frequency and significance in the entire dataset.

* **Stopwords Removal**: I continue to remove common stopwords from the text to reduce noise.
* **Max Features**: We limit the vectorization to the top 5000 features to balance performance and computational cost.
This step converts each review into a sparse matrix that can be fed into machine learning models.

