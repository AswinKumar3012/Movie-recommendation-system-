# Movie-recommendation-system-
Recommender Systems, also labelled as recommendation systems, are statistical algorithms that recommend products to users based on similarities between the buying trends of various user or similarities between the products.

Collaborative Filtering- The process used to calculate similarities between the buying trends of various users or similarities between products is called collaborative filtering.

User based collaborative filtering- If two user X and Y, like products A and B and there is another user Z who likes product A, then the product B will also be recommended to user Z

Item-based collaborative filtering- In this products are recommended based on similarities between themselves. For instance if a user likes product A and product A has properties X and Y, another product B with properties X and Y will also be recommended to the user.
Data Preprocessing- We need a dataframe that consists of userId, movieId, title and ratings
Data Visualisation- Let's first group the dataset by title and see whhat information we can get regarding the ratings of movies
A movie which is rated by large number of people is usually a good movie

Let's create a dataframe that shows the title, mean rating and the rating counts
The above dataframe contains movie title, average rating (ratings mean) and the number of rating_counts

We will plot a histogram to see how the average ratings are distributed.
In the above plot, most of the movies have an average rating between 3 and 4

Distribution for rating counts
There are around 7000 movies with less than 10 rating counts. The number of movies decrease with an increase in ratings counts. Movies with more than 50 rating are very few.

It is also nteresting to see the relationship between mean ratings and rating counts of a movie
From the above graph in the top right portion, you can see that the movies witha higher number of rating counts tend to have higher mean ratings as well.

Let's sort our dataset by rating counts and see the average ratings of the movies with the top 5 highest number of ratings
Item Based Collaborative Filtering
In item based collaborative filtering, products are recommended based on common characteristics.

The first step is to create a dataframe where each movie is represented by a column and rows contain user raings for movies.
The Dataset contains 610 unique users and 9,719 unique movies

Now we will find the movie recommendation based on a single movie and then based on multiple movies.

Finding recommendations based on a single movie- Suppose we want to find the recommendation based on the movie Pulp Fiction.

First we will filter the column that contains the user ratings for the movie.
Next, we will find the correlation between the user ratings of all the movies and the user ratings for the movie pulp fiction
Correlation itself is not giving meaningful results, one solution to this problem can be that in addition to the correlation between the movies, we also use rating counts, for the correlated movie as a criteria for finding the best recommendation.
The pf_corr column contains some NaN values. This is because there can be movies that are rated by users who did not rate Pulp Fiction (1994). In such cases, correlation will be null

We will remove all the movies with null correlation with Pulp Fiction (1994)

A better way is to find the movies with the rating counts of atlease 50 and having the highest correlation with Pulp Fiction (1994)
Finding the recommendation based on multiple movies- In this we will see how to recommend movies to a user based on his ratings of multiple movies. The first step is to create a dataframe, which contains a correlation between all the movies in our dataset in the form of a matrix.
Now supose a new user logs into the website. The user has already watched three movies and has given ratings to those movies.
We will be recommending movies from our dataset based on the ratings by a new user for these three movies
From all_movie_correlations dataframe, let's obtain correlation values for the movies related to Forrest Gump (1994)
To get a final recommendation, you can sort the movies in the descending order of the weighted correlation
