# Hybrid(Collaborative Multiarm Bandits + Content Base Filtering)

# Overview
This repository implements a hybrid recommendation system that combines Collaborative Multiarm Bandits and Content-Based Filtering techniques. The system leverages the advantages of both approaches to provide accurate and diverse recommendations to users. Collaborative Multiarm Bandits allow for adaptive exploration of user preferences, while Content-Based Filtering utilizes item characteristics to make personalized recommendations. By combining these two methods, the system achieves a robust and efficient recommendation mechanism. The repository contains the necessary code and resources to implement and experiment with this hybrid recommendation system.

# Dataset
We utilized the MovieLens dataset, a widely used benchmark dataset for recommendation systems. The dataset contains a large collection of movie ratings provided by users, along with movie metadata such as genre, release year, and tags. This dataset served as the foundation for training and evaluating our recommendation system.

# Data Preprocessing
The user and movie IDs in the ratings dataset are converted to 0-based indices by subtracting 1 from their values. The ratings dataset is merged with the movies dataset based on the movie ID. The resulting merged dataset is then transformed into a pivot table, where rows represent users, columns represent movies, and values represent ratings. Any missing values are filled with zeros. The pivot table is then converted into a NumPy array for further processing.

# Methodology
Our project employs a hybrid approach that combines Collaborative Multiarm Bandits and Content-Based Filtering techniques. Collaborative filtering is used to identify similar users and recommend movies based on their preferences. The multi-armed bandit algorithm allows for a balance between exploring new movie recommendations and exploiting known preferences to optimize the recommendations for individual users.

# Implementation
The implementation code provided in the repository performs the following steps:

•Loads the necessary libraries and datasets (movies and ratings).
•Preprocesses the data by converting user and movie IDs to 0-based indices and creating a pivot table with zero-filled missing values.
•Implements the collaborative multi-armed bandit algorithm:
Defines a function select_movie to choose the next movie to play based on the current values and an exploration parameter.
Defines the main function bandit_collaborative_filtering that initializes the bandit algorithm, sets exploration parameters, and runs the bandit algorithm for a specified number of iterations.
Updates the number of plays and total reward for each movie based on user ratings.
Calculates and updates the value of each movie based on the updated reward and number of plays.
Recommends the top 10 movies based on the final values, excluding already rated movies.
Implements content-based filtering:
Defines a function user_profile to create a user profile based on movie ratings and genres.
Defines a function similarity to calculate the cosine similarity between the user profile and movie profiles.
Defines a function recommendation to recommend movies based on the calculated similarities.
Prompts the user to enter a user ID and retrieves the recommended movies using collaborative multi-armed bandits.
Displays the top 10 recommended movies and the top 3 recommended movies using content-based filtering.
The provided code allows for a hybrid recommendation system that combines the strengths of both Collaborative Multiarm Bandits and Content-Based Filtering techniques to generate accurate and diverse movie recommendations for users.


