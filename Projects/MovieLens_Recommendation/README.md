# Movie Recommender System

## Project Overview

This project builds a hybrid movie recommender system using the MovieLens Small dataset. The system recommends ten movies based on a movie entered by the user.

The recommendation engine combines item-based collaborative filtering with tag-based content similarity. Collaborative filtering captures similarities in user rating behavior, while content-based filtering uses movie tags to identify descriptive similarities between movies.

Fuzzy title matching is also included so the system can recognize close matches when a user does not enter the exact movie title.

## Business Problem

Streaming and entertainment platforms contain large catalogs that can make it difficult for users to decide what to watch. Recommendation systems help reduce this information overload by identifying content that is likely to match a user's interests.

This project explores how movie ratings and descriptive tags can be combined to generate relevant movie recommendations.

## Dataset

The project uses the MovieLens Small dataset from GroupLens.

The following files are used:

- `movies.csv` – movie titles and genres
- `ratings.csv` – user ratings for movies
- `tags.csv` – user-provided descriptive movie tags

The common `movieId` field allows the three datasets to be combined.

## Methods

The project follows these steps:

1. Load the MovieLens datasets
2. Clean movie titles
3. Extract movie release years
4. Aggregate movie tags
5. Calculate average movie ratings
6. Create a user-movie rating matrix
7. Calculate collaborative movie similarity using cosine similarity
8. Convert tags into TF-IDF features
9. Calculate tag-based content similarity
10. Combine the two similarity matrices into a hybrid recommendation model
11. Apply fuzzy title matching
12. Return the top ten recommended movies

## Recommendation Approach

The hybrid similarity model uses:

- **70% collaborative filtering similarity**
- **30% tag-based content similarity**

Collaborative filtering compares how users rate different movies, while content-based filtering compares descriptive movie tags.

The combined approach allows the recommender to use both user behavior and movie metadata.

## Tools and Technologies

- Python
- Jupyter Notebook
- pandas
- NumPy
- scikit-learn
- TF-IDF
- Cosine similarity
- fuzzywuzzy
- tabulate

## Repository Structure

```text
Movie_Recommender_System/
│
├── README.md
│
├── data/
│   ├── movies.csv
│   ├── ratings.csv
│   └── tags.csv
│
└── notebooks/
    └── Movie_Recommender_System.ipynb
```

## How to Run the Project

1. Clone the repository.

2. Place the MovieLens data files inside the `data/` folder:

```text
data/movies.csv
data/ratings.csv
data/tags.csv
```

3. Install the required Python packages:

```bash
pip install pandas numpy scikit-learn fuzzywuzzy python-Levenshtein tabulate
```

4. Open:

```text
notebooks/Movie_Recommender_System.ipynb
```

5. Run the notebook cells in order.

6. Use the interactive recommender or call:

```python
recommend_movies("Toy Story", top_n=10)
```

## Key Skills Demonstrated

- Recommender systems
- Collaborative filtering
- Content-based filtering
- Hybrid recommendation modeling
- Cosine similarity
- TF-IDF text vectorization
- Fuzzy string matching
- Data cleaning and preprocessing
- Python and pandas
- Interactive application development

## Outcome

The project creates an interactive hybrid recommender that accepts a movie title and returns ten related movies. By combining rating-based and tag-based similarity, the system provides recommendations using both user behavior and movie characteristics.

## Limitations

The system is based on the MovieLens Small dataset and therefore represents only the users, movies, ratings, and tags available in that dataset. Movies with limited ratings or tag information may produce weaker recommendations.

The 70/30 weighting between collaborative and content similarity is manually selected and has not been optimized through formal validation.

## Future Improvements

Potential enhancements include:

- Tuning the collaborative/content similarity weights
- Adding genre-based features
- Incorporating user-specific recommendations
- Evaluating recommendation quality with ranking metrics
- Adding popularity and rating thresholds
- Building a web-based recommendation interface
