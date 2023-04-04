# Movie Recommendation System
![angry_bird_in_cinema](https://media4.giphy.com/media/3o7rc0qU6m5hneMsuc/giphy.gif?cid=ecf05e47r1fe3wtme87wmqv8bgihs7wrz4qdinb7hl4rjcjl&rid=giphy.gif&ct=g)

This repository contains a movie recommendation system built using Python and the Surprise library for collaborative filtering and scikit-learn for content-based filtering. The dataset used is from GroupLens and can be found at [MovieLens 25M dataset](https://grouplens.org/datasets/movielens/25m/).

# Dataset Description

The dataset used in this recommendation system is the MovieLens 25M dataset provided by GroupLens. It contains 25 million ratings and one million tag applications applied to 62,000 movies by 162,000 users. The dataset includes the following files:

- `movies.csv`: Contains movie information, including `movieId`, `title`, and `genres`.
- `ratings.csv`: Contains user movie ratings, including `userId`, `movieId`, `rating`, and `timestamp`.
- `links.csv`: Contains identifiers that can be used to link to other sources of movie data, including `movieId`, `imdbId`, and `tmdbId`.

# Recommendation Techniques
The movie recommendation system combines two popular recommendation techniques:

1. **Collaborative Filtering**: A method that predicts a user's preference for an item based on the preferences of similar users. In this project, the Singular Value Decomposition (SVD) algorithm from the scikit-surprise library is used for collaborative filtering.

2. **Content-Based Filtering**: A method that predicts a user's preference for an item based on the item's features and the user's preferences for similar features. In this project, the Term Frequency-Inverse Document Frequency (TF-IDF) approach is used to create a feature vector for movie genres, and the cosine similarity is calculated to measure the similarity between movies based on their genres.

# Table of Contents
## 1. Dependencies
To run the script, you need to install the following libraries:

- scikit-surprise
- pandas
You can install them using pip:
```
pip install scikit-surprise
pip install pandas
```

## 2. Usage

1. Download the dataset from MovieLens 25M dataset and extract the files to the to the same folder as the repository .
2. Change the MovieLens 25M dataset folder name to `data`
3. Run the script `movie_recommended_system.ipynb` using Jupyternotebook

## 3. Code Overview

The code consists of the following steps:

1. Import required libraries and load the dataset
2. Prepare the data for collaborative filtering 
3. Merge the datasets 
4. Build a collaborative filtering model
5. Prepare the data for content-based filtering
6. Create a function for content-based recommendations
7. Combine collaborative and content-based filtering
8. Test the recommendation system

## 4. Testing

To test the recommendation system, follow these steps:

1. Set the user ID, movie title, and the number of recommendations to generate.
2. Call the hybrid_recommendations() function to generate n recommendations for the user based on the provided movie title.
3. The recommendations will be printed as a list of movie titles with their corresponding ranks.
For example: 

```
user_id = 2
title = 'Toy Story (1995)'
n = 10
recommendations = hybrid_recommendations(user_id, title, n)
recommendations_list = recommendations.tolist()
print(f"Top {n} recommendations for User {user_id} who likes '{title}':")
for i, movie_title in enumerate(recommendations_list, start=1):
    print(f"{i}. {movie_title}")
```
This will print the top 10 recommendations for User 2 who likes 'Toy Story (1995)'
![toy_story](https://media0.giphy.com/media/Jr9saevgSxACA/giphy.gif?cid=ecf05e47mhiuv53omrzda4lvqkfezznynkvxa28ts5eqngj1&rid=giphy.gif&ct=g)

![top 10 recommendation for user 2](https://user-images.githubusercontent.com/125786884/225857502-592a8d26-cd05-4324-adf3-62e2b889b254.png)



# Customizing Recommendations
You can customize the recommendation system by modifying the following parameters:

1. **User ID**: Change the user_id variable to the desired user ID to generate recommendations for a specific user.
2. **Movie Title**: Change the title variable to the desired movie title to base the recommendations on a specific movie.
3. **Number of Recommendations**: Change the n variable to the desired number of recommendations to generate a custom number of top recommendations.

For example:

```
user_id = 10
title = 'The Matrix (1999)'
n = 5
recommendations = hybrid_recommendations(user_id, title, n)
```

This will generate the top 5 recommendations for User 10 who likes 'The Matrix (1999)'.

# Contributing
Contributions to improve the movie recommendation system are welcome. You can contribute by:

1. Forking the repository
2. Creating a new branch with your changes
3. Submitting a pull request for review
Please ensure your code follows the established coding style and is well documented.
