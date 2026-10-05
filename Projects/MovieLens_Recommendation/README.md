# Movie Recommender System

## Project Overview

This project builds a hybrid movie recommender system using the MovieLens Small dataset.

The system combines item-based collaborative filtering with tag-based content similarity to recommend ten movies based on a movie entered by the user.

## Business Problem

Streaming and entertainment platforms contain large catalogs that can make it difficult for users to decide what to watch.

This project is aimed at accomplishing the following goals:

- Use movie ratings to identify similar viewing patterns.
- Use descriptive movie tags to identify content similarity.
- Combine collaborative and content-based filtering.
- Support fuzzy title matching for easier user input.
- Return ten related movie recommendations.

## Dataset

The project uses the MovieLens Small dataset.

The following files are used:

- `movies.csv`
- `ratings.csv`
- `tags.csv`

The common `movieId` field allows the three datasets to be combined.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- TF-IDF
- Cosine Similarity
- fuzzywuzzy
- tabulate

## Project Workflow

The project follows these main steps:

1. **Data Loading**
   - Loaded movie, rating, and tag data.

2. **Movie Title Preparation**
   - Cleaned movie titles.
   - Extracted release years.

3. **Tag Processing**
   - Aggregated user-provided tags at the movie level.

4. **Rating Analysis**
   - Calculated average movie ratings.
   - Created a user-movie rating matrix.

5. **Collaborative Filtering**
   - Calculated item-based cosine similarity using rating behavior.

6. **Content-Based Filtering**
   - Converted movie tags into TF-IDF features.
   - Calculated tag-based cosine similarity.

7. **Hybrid Recommendation Model**
   - Combined 70% collaborative similarity with 30% tag-based similarity.

8. **Fuzzy Matching and Recommendation**
   - Matched approximate movie titles.
   - Returned the top ten recommended movies.

## Recommendation Approach

The hybrid recommendation model uses:

- 70% collaborative filtering similarity
- 30% tag-based content similarity

This allows the recommender to use both user behavior and movie characteristics.

## Key Findings

The project demonstrates that rating behavior and movie metadata can be combined to generate relevant movie recommendations.

The hybrid approach provides a more flexible recommendation process than relying on either ratings or tags alone.

## Outcome

The project creates an interactive movie recommender that accepts a movie title and returns ten related movies.

The final system demonstrates collaborative filtering, content-based filtering, text vectorization, similarity modeling, and fuzzy matching.

## Installation / Running the Project

1. Clone the repository:

```bash
git clone <repo_url>
cd <repository_name>
```

2. Place the MovieLens files in the `data/` folder.

3. Install the required packages:

```bash
pip install -r requirements.txt
```

4. Launch Jupyter Notebook:

```bash
jupyter notebook
```

5. Open and run:

`notebooks/Movie_Recommender_System.ipynb`
