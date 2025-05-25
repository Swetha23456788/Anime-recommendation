# Anime-recommendation
anime recommendation using tf idf vectorization and genre filtering.


![image](https://github.com/user-attachments/assets/6b9a080f-fd75-4a94-8f0d-8cac588990da)
image source: Freepik





🎌 Anime Recommender System

A content-based recommender system that suggests similar anime based on **plot (synopsis)** and **genres**. The model uses **NLP techniques** and TF-IDF vectorization to understand the storyline of an anime, then combines that with **genre similarity** to recommend new titles while **avoiding recommending other entries from the same franchise** (e.g., not recommending Naruto Shippuden for Naruto).



## 📁 Dataset

- **Source**: [anime-dataset-2023.csv](#) (kaggle notebook)
- **Size**: 24,000+ anime entries
- **Columns Used**:
  - `Name`: Main title of the anime
  - `Synopsis`: Short plot summary
  - `Genres`: Comma-separated genres
  - *(Other columns available but unused in current version)*


## 🔍 Features

- 🔤 **Preprocessing**: Lowercasing, tokenization, lemmatization, stopword removal
- 🧠 **TF-IDF Vectorization**: Transforms the cleaned synopsis into vector form
- 🤝 **Cosine Similarity**: Measures how similar the plot vectors are
- 🧩 **Genre Similarity**: Jaccard Index for comparing genre sets
- 🧪 **Hybrid Score**: Combines plot and genre similarity into a single score
- 🚫 **Franchise Filter**: Filters out anime with the same core franchise name (e.g., other "Naruto" series)
- 📋 **Tabular Output**: Recommendations are printed using `tabulate` for clean readability

---

## 🛠️ Installation & Setup

1. Clone the repo or copy the notebook
2. Install dependencies:

```bash
pip install pandas scikit-learn nltk tabulate
```

3. Download required NLTK data (in script already):

```python
import nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('wordnet')
nltk.download('stopwords')
```


## 🚀 How It Works

1. **Data Load**: Loads anime data and filters down to essential columns.
2. **Preprocessing**: Cleans and tokenizes each synopsis.
3. **TF-IDF Vectorization**: Converts plots into numerical vectors.
4. **Genre Parsing**: Converts genre strings into sets.
5. **Similarity Computation**:

   * Cosine similarity for plot
   * Jaccard similarity for genres
   * Combined similarity = `0.7 * plot + 0.3 * genre`
6. **Recommendation Logic**:

   * Excludes entries that share the main title (e.g., avoids recommending sequels)
   * Sorts by highest combined similarity


## 📌 Requirements

* Python 3.7+
* pandas
* scikit-learn
* nltk
* tabulate

## ✅ To Do (Ideas for Future Improvements)

* Add Streamlit UI (already prototyped)
* Use a model like BERT for deeper plot understanding
* Include user ratings in ranking recommendations
* Collaborative filtering version (based on user behavior)
