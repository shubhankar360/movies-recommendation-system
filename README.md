# Movie Recommendation System

A content-based movie recommendation system built using Python, Pandas, Scikit-learn, and Natural Language Processing (NLP).

The project recommends movies similar to a given movie by analyzing metadata such as genres, keywords, cast members, directors, and movie overviews. Similarity between movies is calculated using vectorization and cosine similarity techniques.

## Overview

This recommendation engine uses content-based filtering, meaning recommendations are generated based on the characteristics of movies rather than user ratings or watch history.

The model combines multiple movie attributes into a single textual representation and then applies NLP techniques to find movies with similar content.

## Dataset

The project uses the TMDB 5000 Movie Dataset:

- `tmdb_5000_movies.csv`
- `tmdb_5000_credits.csv`

The datasets contain information such as:

- Movie title
- Overview
- Genres
- Keywords
- Cast
- Crew

## Features

- Content-based movie recommendations
- NLP preprocessing pipeline
- Feature extraction using Count Vectorization
- Text normalization and stemming
- Similarity calculation using Cosine Similarity
- Fast recommendation retrieval
- Model serialization using Pickle

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- NLTK
- Pickle

## Project Workflow

### 1. Data Collection

Load movie and credits datasets and merge them based on movie titles.

### 2. Data Cleaning

- Remove unnecessary columns
- Handle missing values
- Remove duplicates

### 3. Feature Engineering

Extract relevant information from:

- Genres
- Keywords
- Cast
- Crew
- Overview

Combine these attributes into a single feature called `tags`.

### 4. Text Preprocessing

- Convert text to lowercase
- Remove spaces between multi-word entities
- Apply stemming using NLTK's Porter Stemmer

### 5. Vectorization

Convert processed text into numerical vectors using:

```python
CountVectorizer(max_features=5000, stop_words='english')
```

### 6. Similarity Calculation

Use cosine similarity to measure the closeness between movie vectors.

```python
cosine_similarity(vectors)
```

### 7. Recommendation Generation

Given a movie title:

1. Find the movie index
2. Retrieve similarity scores
3. Sort movies by similarity
4. Return the top recommendations

## Example

Input:

```python
recommend("Batman Begins")
```

Output:

```text
The Dark Knight
Batman
Batman Returns
Batman Forever
Batman & Robin
```

## Project Structure

```text
Movie-Recommendation-System/
│
├── movie-recomender-system.ipynb
├── tmdb_5000_movies.csv
├── tmdb_5000_credits.csv
├── movie_dict.pkl
├── movies.pkl
├── README.md
```

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/movie-recommendation-system.git
```

Move into the project directory:

```bash
cd movie-recommendation-system
```

Install dependencies:

```bash
pip install pandas numpy scikit-learn nltk
```

## Running the Project

Open the notebook:

```bash
jupyter notebook
```

Run all cells in:

```text
movie-recomender-system.ipynb
```

## Future Improvements

- Add collaborative filtering
- Integrate TMDB API for movie posters
- Build a web interface using Streamlit
- Deploy the application online
- Improve recommendation accuracy using embeddings and transformer models

## Learning Outcomes

Through this project, I gained experience in:

- Data preprocessing
- Feature engineering
- Natural Language Processing
- Vectorization techniques
- Similarity-based recommendation systems
- Model serialization
- Building end-to-end machine learning pipelines

## License

This project is open-source and available under the MIT License.
