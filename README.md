# Movie-Recommendation-System-using-cosine-similarity
For a **Movie Recommendation System**, the README should explain the "Magic" of how a computer understands that two movies are similar. Since you are using **Cosine Similarity**, focusing on the vector space model is key.

---

## 🎬 Movie Recommendation System using Cosine Similarity

### 📋 Overview

This project is a **Content-Based Filtering** recommendation system. It suggests movies to users by calculating the similarity between items based on their metadata (genres, keywords, cast, and crew). Unlike collaborative filtering, this system relies on the attributes of the movies themselves to make accurate suggestions.

### 🧠 The Logic: Why Cosine Similarity?

In this system, every movie is converted into a mathematical vector in a multi-dimensional space. To find how similar two movies are, we calculate the **cosine of the angle** between their vectors.

* **Angle is Small**: The cosine value is close to 1, meaning the movies are highly similar.
* **Angle is 90°**: The cosine value is 0, meaning the movies are not similar at all.

---

### 🚀 Key Features

* **Metadata Tagging**: Combines movie genres, overview, and cast into a single "tags" column.
* **Text Vectorization**: Uses `CountVectorizer` (Bag of Words) or `TF-IDF` to turn text into numerical data.
* **Similarity Engine**: Computes a  similarity matrix allowing for near-instant recommendations.
* **Top-N Recommendations**: Returns the top 5 or 10 most relevant movies for any given input.

---

### 🛠️ Tech Stack

* **Language**: Python 3.x
* **Data Handling**: `pandas`, `numpy`
* **Machine Learning**: `scikit-learn` (for `CountVectorizer` and `cosine_similarity`)
* **Dataset**: Typically the [TMDB 5000 Movie Dataset](https://www.kaggle.com/tmdb/tmdb-movie-metadata).

---

### ⚙️ Workflow

1. **Data Cleaning**: Handle missing values and convert strings of lists (genres/cast) into usable keywords.
2. **Stemming**: Reduce words to their root form (e.g., "actions" and "action" become the same) using NLTK's `PorterStemmer`.
3. **Vectorization**: Create a sparse matrix where each row represents a movie and each column a unique word.
4. **Similarity Calculation**: Run the Cosine Similarity algorithm on the matrix.
5. **Recommendation**: Sort the similarity scores in descending order for the selected movie.

---

### 📦 Quick Start

1. **Clone the repository**:
```bash
git clone https://github.com/your-username/Movie-Recommendation-Cosine.git

```


2. **Basic Usage**:
```python
from sklearn.metrics.pairwise import cosine_similarity

# Calculate similarity matrix
similarity = cosine_similarity(vectors)

# Get recommendations for "The Dark Knight"
def recommend(movie):
    index = movies[movies['title'] == movie].index[0]
    distances = sorted(list(enumerate(similarity[index])), reverse=True, key=lambda x: x[1])
    for i in distances[1:6]:
        print(movies.iloc[i[0]].title)

```



---

### 📊 Results Example

**Input Movie:** `The Avengers`

**Top 5 Recommendations:**

1. Avengers: Age of Ultron
2. Iron Man 3
3. Captain America: Civil War
4. Captain America: The First Avenger
5. Thor: The Dark World

---

