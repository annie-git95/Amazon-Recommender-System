# Amazon-Recommender-System
A Recommender System for better Food & Groceries selection

In this project, we have explored multiple Content Based and Collaborative Filtering approaches.

## CHALLENGE?
Many items, Few transactions -> Sparce Matrices 

## Collaborative Filtering:
User Based: User’s who bought this, also bought that…
Item Based: If you like this item, you may also like that item…

Collaborative Filtering works by recommending you the things that others users with similar interests have also liked.
Our research on this topic spans three primary types of algorithms:
1. Similarity: Similarity algorithms, such as cosine similarity, are appealing for their simplicity, ease of use, and swift deployment.
2. Clustering: Clustering algorithms, specifically k-Nearest Neighbors (KNN), evolve beyond similarity methods in that they are Machine Learning models that are fit to training data. While KNN is a widely known algorithm for recommender system applications, handling large amounts of data can slow it down substantially. Additionally, in the case of the Amazon Grocery data set, the data was imbalanced, a known hinderance to KNN performance, as it consisted primarily of 5-star reviews.
3. Matrix Factorization: Three matrix factorization algorithms were researched and tested: Singular Value Decomposition (SVD), SVD++, and Non-Negative Matrix Factorization (NMF). 


Problem with Collaborative Filtering: Cold Start
Solution: Content Based Recommendation System

## Content Based Approach:
Determine relative ‘closeness’ of items based on their description and recommend based on this. In content-based filtering, recommendations are derived from the characteristics of the content being pursued.
The process begins by creating a pivot table with all products representing the columns, users representing the rows and any given ratings representing the values. As there will likely be a lot of products each user did not rate, these values are represented by NaN.
Because we cannot use NaN in calcuations, and also because the users were asked to rate products on a 1-5 scale, we can transform any NaN value into a 0.

After data transformation, Matrix Factorization and Stochastic Gradient Descent were used to create predicted ratings for each product, for each user.

Matrix Factorization on a high level is producing two matrices whose product is the original matrix given. The two matrices represent generated item and user features. The features are inferred from their related rating patterns. High correspondence between item and user factors lead to a recommendation.

Within the Matrix Factorization process, Stochastic Gradient Descent is used to avoid imputation and overfitting. This approach helps to model directly the observed ratings only, and generalizes these ratings in such a way that predicts future ratings. A minimum squared error is used to find the expected rating and to avoid overfitting, a constant is applied to control the extent of regularization. 


The notebook contains helpful notes and explanation of appraoches. 
