# Rtr Review Prediction and Item Recommender

## Overview 

### Goal 
The goal of this project is to predict ratings on Rent The Runway items based on existing user reivew data. We also wanted to build a recommender to recommend new users items we think they would like based on existing ratings.

### Data 
The dataset was downloaded from [UCSD Recommeder Systems Datasets](https://cseweb.ucsd.edu/~jmcauley/datasets.html?fbclid=IwAR3v3VTIIMAIk3HN0AAb3u8MlTVkSdIbWrq41ilT6SsQBltP7fJrIShEIAM#clothing_fit) with 190k reviews, 100k  users on 5.8k items.

## Review Prediction

To predict the rating, I had the Baseline model always predict the mean rating. With that, I got a RMSE of 0.7146. After that, I also tried different regression algorithms: linear regression, decision tree, and random forest. 

Random forest had the best performance with an RMSE of 0.6824.

|  | Baseline | Linear Regression 1 | Linear Regression 2 | Decision Tree | Random Forest |
| --- | --- | --- | --- |--- |--- |
| RMSE | 0.7146 | 0.6912 | 0.6889 | 0.6854 | 0.6823 |

## Items Recommeder

The recommender was built for new users. 
1. New users are prompted to put in their user profile (height, weight, age, size).
2. Recommender searched for the 100 most similar users in the dataset using consine similarity.
3. Recommender returns the top 10 rated items based on a calculated weighted average (with a added reward for items that are reviewed more frequently).
