# Movie-Recommendation-System
A content-based movie recommendation system built with Python, utilizing movie genres and user ratings to suggest similar movies. The project processes the MovieLens dataset, performs data cleaning, and creates a user profile based on genre preferences to generate personalized movie recommendations using weighted genre scores
# Content-Based Movie Recommendation System
## Overview
This project implements a content-based movie recommendation system using the MovieLens dataset. It leverages movie genres and user ratings to recommend movies that align with a user's preferences. The system processes movie data, extracts genres, builds a user profile based on rated movies, and generates recommendations by computing weighted genre scores. The project is built using Python with libraries like Pandas, NumPy, and Matplotlib for data manipulation and visualization.

## Features
- Data Preprocessing: Loads and cleans the MovieLens dataset (movies.csv and ratings.csv), extracting movie titles, release years, and genres.
- Genre Encoding: Converts genres into a binary matrix for each movie, enabling content-based filtering.
- User Profile Creation: Constructs a user profile by weighting genres based on user-provided movie ratings.
- Recommendation Engine: Generates movie recommendations by calculating similarity scores between the user profile and movie genres.
- Visualization: Uses Matplotlib for potential visualization of data (configurable for further analysis).

## Dataset
The project uses the MovieLens dataset, consisting of two main files:
- movies.csv: Contains movie details with columns:
  - `movieId`: Unique identifier for each movie.
  - `title`: Movie title with release year.
  - `genres`: Pipe-separated list of genres (e.g., Adventure|Comedy|Fantasy).


- ratings.csv: Contains user ratings with columns:
  - `userId`: Unique identifier for each user.
  - `movieId`: Movie identifier.
  - `rating`: User rating (0.5 to 5.0).
  - `timestamp`: Rating timestamp (dropped during preprocessing).
The dataset includes 34,208 movies with 20 unique genres, such as Adventure, Comedy, Drama, Sci-Fi, and Thriller.

## Requirements
- Python 3.11
- Libraries: `pandas`, `numpy`, `matplotlib`, `re`

## Installation
1.Clone the repository:
```bash
git clone https://github.com/yourusername/movie-recommendation-system.git
```
2.Install dependencies:
```bash
pip install -r requirements.txt
```
3.Run the Jupyter Notebook:
```bash
jupyter notebook movies(content based).ipynb
```

## Usage
- Load and preprocess the movies.csv and ratings.csv datasets.
- Input a list of movies with user ratings (e.g., "Toy Story" with a rating of 3.5).
- Generate a user profile based on the genres of rated movies.
- Compute recommendation scores for all movies and output the top recommendations.

## Example
The system takes a user input like:
userInput = [
    {'title': 'Breakfast Club, The', 'rating': 5},
    {'title': 'Toy Story', 'rating': 3.5},
    {'title': 'Jumanji', 'rating': 2},
    {'title': 'Pulp Fiction', 'rating': 5},
    {'title': 'Akira', 'rating': 4.5}
]

It then recommends movies like:
- Space Jam (1996)
- Mulan (1998)
- Who Framed Roger Rabbit? (1988)
- The Lego Movie (2014)

## Methodology
- Data Cleaning: Extracts release years from movie titles using regex and splits genres into lists.
- Genre Matrix: Creates a binary matrix for genres (1 if a movie belongs to a genre, 0 otherwise).
- User Profile: Computes a weighted sum of genres based on user ratings using matrix multiplication.
- Recommendation: Calculates a score for each movie by multiplying the genre matrix with the user profile and normalizing by the sum of user profile weights. - Movies are sorted by score to provide recommendations.

## Future Improvements
- Incorporate additional features like movie tags or plot summaries for more robust recommendations.
- Implement cosine similarity or other distance metrics for improved recommendation accuracy.
- Add visualization of genre distributions or recommendation scores.
- Integrate collaborative filtering to combine content-based and user-based approaches.
