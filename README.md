# Restaurant Review Sentiment Analysis

A Natural Language Processing (NLP) project that classifies restaurant reviews as **positive** or **negative** using three machine learning models: Logistic Regression, Naive Bayes, and Support Vector Machine (SVM).

This project was completed as part of the Artificial Intelligence module during our degree.

## Authors

- Kek Quan Feng
- Chan Yong Jie
- Lo Yong Sheng

## Project Overview

The pipeline covers the full NLP workflow:

1. **Data loading** — restaurant review dataset (`Restaurant_Reviews.tsv`)
2. **Text preprocessing** — lowercasing, contraction expansion, negation handling, removal of numbers and punctuation, deduplication
3. **Exploratory data analysis** — class distribution, review length analysis, word cloud visualization
4. **Feature extraction** — `CountVectorizer` + `TfidfTransformer` (TF-IDF)
5. **Model training** — Logistic Regression, Multinomial Naive Bayes, SVM
6. **Hyperparameter tuning** — `GridSearchCV` for each model
7. **Evaluation** — accuracy, precision, recall, F1-score, confusion matrix, ROC curves
8. **External validation** — testing trained models on a separately crawled Yelp dataset (`yelp_reviews.xlsx`)
9. **GUI** — a Tkinter-based interface for live sentiment prediction
10. **Web scraping** — Yelp review scraper using `requests` + `BeautifulSoup`

## Results

| Model               | Accuracy (Test Set) |
|---------------------|---------------------|
| Logistic Regression | ~79%                |
| Naive Bayes (tuned) | ~82%                |
| SVM (tuned)         | ~81%                |

## Datasets

- `Restaurant_Reviews.tsv` — 1,000 labeled restaurant reviews (1 = positive, 0 = negative)
- `yelp_reviews.xlsx` — 448 Yelp reviews used for external validation

## How to Run

### 1. Install dependencies

```bash
pip install pandas numpy scikit-learn matplotlib seaborn wordcloud nltk contractions beautifulsoup4 requests openpyxl
```

### 2. Download NLTK data

In a Python shell:

```python
import nltk
nltk.download('stopwords')
```

### 3. Open the notebook

```bash
jupyter notebook sentiment_analysis.ipynb
```

Run all cells from top to bottom.

## Project Structure

```
.
├── sentiment_analysis.ipynb    # Main notebook
├── Restaurant_Reviews.tsv      # Training dataset
├── yelp_reviews.xlsx           # External validation dataset
├── .gitignore
└── README.md
```

## Tech Stack

- **Python 3**
- **scikit-learn** — ML models, vectorization, evaluation
- **NLTK** — stopwords, stemming
- **pandas / numpy** — data handling
- **matplotlib / seaborn / wordcloud** — visualization
- **BeautifulSoup / requests** — web scraping
- **Tkinter** — GUI
