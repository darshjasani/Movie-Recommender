I have use collaborative filtering to build a recommender system for movies.

The dataset consists of ratings on a scale of 1 to 5. The dataset has nu = 943 users, and
nm = 1682 movies. 
I have been working with the script ex8 cofi.m. I have implement the function cofiCostFunc.m
that computes the collaborative fitlering objective function and gradient. 

Af-ter implementing the cost function and gradient, i have  used fmincg.m to
learn the parameters for collaborative filtering.

The matrix Y (a num movies X num users matrix) stores the ratings y(i;j)
(from 1 to 5). The matrix R is an binary-valued indicator matrix, where
R(i; j) = 1 if user j gave a rating to movie i, and R(i; j) = 0 otherwise. 

The objective of collaborative filtering is to predict movie ratings for the movies
that users have not yet rated, that is, the entries with R(i; j) = 0. This will
allow us to recommend the movies with the highest predicted ratings to the
user.


To understand the matrix Y, the script ex8 cofi.m will compute
the average movie rating for the first movie (Toy Story) and output the
average rating to the screen.

The collaborative filtering algorithm in the setting of movie recommen-
dations considers a set of n-dimensional parameter vectors x(1); :::; x(nm) and
theta(1); :::; theta(nu), where the model predicts the rating for movie i by user j as
y(i;j) = (theta(j))T x(i).

Given a dataset that consists of a set of ratings produced
by some users on some movies, to learn the parameter vectors
x(1); :::; x(nm); theta(1); :::; theta(nu) that produce the best fit (minimizes the squared
error).

Note that the function returns the gradient for both sets of variables
by unrolling them into a single vector. After completion of the code
to compute the gradients, the script ex8 cofi.m will run a gradient check
(checkCostFunction) to numerically check the implementation the gra-
dients. If the implementation is correct, it  should have the analytical
and numerical gradients match up closely.
