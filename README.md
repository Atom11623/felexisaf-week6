# Twitter Data Preprocessing Project

## Project Overview
This project focuses on preprocessing Twitter data from the **WeRateDogs dataset**, provided by Udacity. The dataset consists of tweets containing various metadata, including timestamps, sources, and textual content. The primary objective of this project is to clean and preprocess the dataset for Natural Language Processing (NLP) tasks such as sentiment analysis, text classification, and exploratory data analysis. The preprocessing ensures that the text data is structured, noise-free, and ready for further modeling.

## Dataset Information
- **Dataset Name:** WeRateDogs Twitter Dataset (Udacity)
- **File Used:** `twitter.csv`
- **Primary Column:** `text` (contains tweet content)
- **Additional Processed Column:** `source`
- **Columns Removed:**
  - `in_reply_to_status_id`
  - `in_reply_to_user_id`
  - `timestamp`
  - `retweeted_status_id`
  - `retweeted_status_user_id`
  - `retweeted_status_timestamp`
  - `expanded_urls`

## Preprocessing Workflow
The dataset undergoes a series of preprocessing steps to refine the textual data and enhance its usability for NLP tasks. The following key steps are applied:

1. **Lowercasing**: Converts all text to lowercase to ensure uniformity.
2. **Removing URLs**: Extracts and removes any links (`http://` or `https://`) to prevent irrelevant content from interfering with analysis.
3. **Removing Punctuation**: Eliminates unnecessary punctuation using `string.punctuation`.
4. **Removing Stopwords**: Filters out common stopwords (e.g., "and", "the", "is") using the `nltk` library to improve model efficiency.
5. **Removing Emojis**: Uses regex to remove emojis and pictographs that may not contribute to textual meaning.
6. **Lemmatization**: Converts words to their base form (e.g., "running" → "run") using `spaCy` to maintain consistency.
7. **Cleaning Source Column**: Extracts the platform name (e.g., "Twitter for iPhone") from HTML-formatted sources to ensure clarity.

## Technologies and Dependencies
The preprocessing pipeline is implemented in Python, leveraging the following libraries:

- **`pandas`** – for data manipulation and handling
- **`string`** – for punctuation removal
- **`re`** – for regex-based text processing
- **`nltk`** – for stopword removal
- **`spacy`** – for advanced NLP tasks, including lemmatization

### Installation
To install the required dependencies, execute the following commands:
```bash
pip install pandas nltk spacy
python -m spacy download en_core_web_sm
```

## Execution

The script processes the dataset and outputs a cleaned version saved as `cleaned_twitter.csv`.


## Use Cases and Applications
The cleaned dataset can be used for:
- Sentiment analysis of tweets
- Text classification (e.g., categorizing tweets by topics)
- Named Entity Recognition (NER) tasks
- Training machine learning models for NLP
- Social media trend analysis