# Sentiment Analysis — Task 4

An end-to-end NLP sentiment classification project built on combined Twitter datasets (`twitter_training.csv` and `twitter_validation.csv`) to classify text into sentiment categories (`Negative`, `Positive`, `Neutral`, and `Irrelevant`).

## Dataset Overview
- **Combined shape:** `75,682` rows and `4` columns (`Tweet_ID`, `Entity`, `Sentiment`, `Tweet_Text`)
- **Initial class distribution:**
  - `Negative`: `22,808`
  - `Positive`: `21,109`
  - `Neutral`: `18,603`
  - `Irrelevant`: `13,162`
- **After cleaning & filtering:** Dropped `686` missing text rows and empty post-cleaning rows, leaving **`73,263`** usable samples.

## Workflow & Pipeline
1. **Load & Inspect Data:** Combined training and validation files and checked class counts.
2. **Text Preprocessing (`NLTK`):** Lowercased text, removed URLs, mentions, hashtags, punctuation, and digits, tokenized tweets, removed English stopwords, and applied `WordNetLemmatizer`.
3. **Feature Extraction (`TF-IDF`):** Converted `Clean_Text` into numerical features using `TfidfVectorizer(max_features=5000, ngram_range=(1, 2))`, producing a `(73263, 5000)` matrix.
4. **Train/Test Split (`80/20`):** Split data with `stratify=y` (`58,610` training samples and `14,653` test samples).
5. **Model Training & Evaluation:** Trained and evaluated **Multinomial Naive Bayes** and **Logistic Regression** using Accuracy, Precision, Recall, F1-Score, and Confusion Matrices.
6. **Visualisation:** Plotted sentiment class distribution and top recurring words across sentiment classes.
7. **Error Analysis:** Examined misclassified test examples (`4,560` total errors for Logistic Regression) to understand ambiguity, short text, and overlapping vocabulary.
8. **Conclusion:** Summarised model comparison and real-world applications.

## Model Results (`14,653` Test Samples)

| Model | Accuracy | Precision (weighted) | Recall (weighted) | F1-Score (weighted) |
| :--- | :---: | :---: | :---: | :---: |
| **Multinomial Naive Bayes** | `0.6391` | `0.6460` | `0.6391` | `0.6278` |
| **Logistic Regression** | `0.6888` | `0.6868` | `0.6888` | `0.6857` |

## Key Takeaways & Real-World Application
- **Best Model:** **Logistic Regression** outperformed **Multinomial Naive Bayes** across all overall evaluation metrics (`0.6888` accuracy vs. `0.6391`).
- **Real-World Use Case:** Useful for **brand monitoring and customer feedback analysis**, helping teams track audience sentiment on social media or reviews, catch negative feedback early, and improve products or support.

## Tech Stack
- Python, `pandas`, `numpy`, `matplotlib`, `seaborn`
- `nltk`
- `scikit-learn` (`TfidfVectorizer`, `train_test_split`, `MultinomialNB`, `LogisticRegression`, metrics)
- Jupyter Notebook / VS Code
