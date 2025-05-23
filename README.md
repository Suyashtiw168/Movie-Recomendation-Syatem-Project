# Movie-Recomendation-Syatem-Project
* Movie Recommendation System — Project Overview
- Objective
The aim of this project is to design and implement a content-based movie recommendation system that suggests films with similar themes and genres. The system analyzes textual metadata such as movie overviews and genres to compute similarity scores and generate recommendations.

- Dataset Description
The project utilizes a dataset titled “New Movies Dataset.csv”, which contains essential metadata for a collection of movies. The relevant attributes extracted for modeling include:

id: Unique identifier for each movie

title: Name of the movie

overview: Brief plot description

genre: Associated genres for the movie

- Data Preprocessing & Feature Engineering
Data Loading & Inspection: Initial data exploration includes checking data types, inspecting missing values, and reviewing dataset structure using standard Pandas functions (head(), info(), describe()).

Feature Selection: Only the columns necessary for content-based filtering (id, title, overview, genre) are retained.

Feature Combination: A new feature, tags, is engineered by concatenating the overview and genre fields. This unified textual field serves as the basis for similarity computation.

- Modeling Approach
Text Vectorization:

Applied CountVectorizer from Scikit-learn to transform textual data into a numerical matrix using the bag-of-words technique.

Parameters used:

max_features=10,000

stop_words='english'

Similarity Calculation:

Computed cosine similarity between movie vectors to measure content similarity.

- Recommendation Functionality
A dedicated function, recommand(movie_name), is developed to:

Retrieve the index of the specified movie

Compute similarity scores

Return the top 5 most similar movie titles based on cosine similarity

Example usage:

python
Copy
Edit
recommand("The Godfather")
- Model Serialization
To support efficient deployment and reuse, the processed data and similarity matrix are serialized using pickle:

movies_list.pkl: Contains the movie metadata and tags

similarity.pkl: Stores the precomputed similarity matrix

- Project Outcome
This project results in a fully functional, content-based recommendation engine capable of suggesting similar movies using textual analysis. It forms a foundational system that can be further enhanced with additional metadata (e.g., cast, director, user ratings) or extended into a hybrid recommendation framework.









