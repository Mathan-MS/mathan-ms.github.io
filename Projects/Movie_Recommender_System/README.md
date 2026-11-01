# Hybrid Movie Recommendation System

## Project Overview

This project develops a hybrid movie recommendation system using the MovieLens Small dataset. It combines item-based collaborative filtering from user ratings with content-based similarity from user-generated movie tags to recommend ten movies related to a title entered by the user.

The system also uses fuzzy title matching to accommodate approximate movie names and presents recommendations with release years and average ratings.

## Business Problem

Streaming and entertainment platforms offer extensive movie catalogs, making content discovery challenging. Recommendation systems can help users find relevant titles by combining patterns in audience preferences with descriptive information about movies.

This project is aimed at accomplishing the following goals:

- Identify relationships between movies using user rating patterns.
- Extract content similarity from descriptive movie tags.
- Combine collaborative and content-based similarities in a hybrid model.
- Support approximate movie-title searches using fuzzy matching.
- Generate and display ten ranked movie recommendations.

## Dataset

The project uses three files from the **MovieLens Small** dataset, included in the project's `data/` folder:

- `movies.csv` — movie identifiers, titles, and genres.
- `ratings.csv` — user identifiers, movie identifiers, ratings, and timestamps.
- `tags.csv` — user-generated movie tags and timestamps.

The shared `movieId` field connects the datasets. The notebook constructs a user–movie rating matrix containing **610 users and 9,724 movies with recorded ratings**.

## Tools & Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- TF-IDF vectorization
- Cosine similarity
- fuzzywuzzy and python-Levenshtein
- tabulate

## Project Workflow

The project follows these main steps:

1. **Data Loading**
   - Loaded the movie, rating, and tag datasets.

2. **Movie Title Preparation**
   - Standardized movie titles and extracted release years.

3. **Tag Processing**
   - Aggregated user-provided tags into movie-level text descriptions.

4. **Rating Analysis**
   - Calculated average movie ratings.
   - Created a 610 × 9,724 user–movie rating matrix, using zero to represent missing ratings for similarity calculations.

5. **Collaborative Filtering**
   - Transposed the rating matrix and calculated item-based cosine similarity from user rating patterns.

6. **Content-Based Filtering**
   - Converted aggregated tags into TF-IDF features and calculated tag-based cosine similarity.

7. **Hybrid Recommendation Model**
   - Combined **70% collaborative similarity** and **30% tag-based similarity** for movies represented in both similarity matrices.

8. **Recommendation and Interactive Testing**
   - Used fuzzy matching to identify the requested movie.
   - Returned ten ranked recommendations with release years and average ratings.
   - Tested interactive title entry and the exit command.

## Recommendation Approach

The hybrid model combines two complementary signals:

- **Collaborative filtering (70%):** Movies are considered similar when their rating patterns across users are similar.
- **Content-based filtering (30%):** Movies are considered similar when their user-generated tags contain related terms.

The weighting is a design choice used in this implementation; it has not been optimized through comparative evaluation. Average ratings are displayed for context but **do not determine recommendation order**.

## Key Findings

- **Rating matrix:** The analysis produces a **610 × 9,724** user–movie matrix, illustrating the sparse nature of user rating data.
- **Movie ratings:** *Toy Story* has an average recorded rating of approximately **3.92**, while *Jumanji* has approximately **3.43**.
- **Hybrid similarity:** The displayed hybrid similarity between *Toy Story* and *Jumanji* is approximately **0.287**, reflecting the weighted combination of the two similarity methods.
- **Recommendation example:** Entering *Toy Story* returns ten recommendations. The first two are *A Bug's Life* (1998) and *Toy Story 2* (1999). Other results include *Jurassic Park*, *The Lion King*, and *Forrest Gump*, demonstrating that shared audience rating patterns can connect movies across different genres.
- **Interactive testing:** An input containing *Toy Story 2* with extra whitespace is matched to *Toy Story 2*. The system then returns ten recommendations, including *A Bug's Life*, *Toy Story*, *The Incredibles*, and *Finding Nemo*. Entering `exit` terminates the session successfully.

## Outcome

The project implements a functional hybrid recommendation workflow that integrates user ratings, text-based movie metadata, similarity modeling, fuzzy title matching, and ranked recommendations. It demonstrates how multiple data sources can support content discovery in a streaming or entertainment setting.

The saved notebook outputs demonstrate that recommendations can be generated successfully. However, the notebook does not evaluate recommendation accuracy with held-out data or ranking metrics, so the results should be interpreted as a working prototype rather than evidence of superior recommendation performance.

## Limitations

User ratings are sparse, and not every movie has descriptive tags. Fuzzy matching may select an unintended title for ambiguous searches. The 70/30 similarity weighting has not been tuned, and the project does not report held-out metrics such as precision@K or recall@K. Future work could evaluate alternative weightings, improve title confirmation, and measure recommendation quality against a baseline.

## Installation / Running the Project

### Prerequisites

- Python 3.11 (recommended, subject to dependency compatibility)
- Git

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
cd mathan-ms.github.io/Projects/Movie_Recommender_System
```

### Step 2: Install Project Dependencies

```bash
python -m pip install -r requirements.txt
```

The three MovieLens CSV files are included in the project's `data/` folder.

### Step 3: Launch Jupyter Notebook

```bash
python -m notebook
```

### Step 4: Open and Run the Notebook

Open `notebooks/Movie_Recommender_System.ipynb`, select the appropriate Python kernel, and choose **Kernel → Restart Kernel and Run All Cells**.

The final interactive cell prompts for a movie title. Enter a movie name to receive recommendations, or type `exit` to finish. Execution time may vary depending on system hardware and available resources.
