# Recommendation-System
Models of Movie Recommendation Systems made in Python using Collaborative Filtering and Matrix Factorization Techniques

Using the [Data Set of the MovieLens 20M Dataset Kaggle Competition](https://www.kaggle.com/grouplens/movielens-20m-dataset), two different kinds of Movie Recommendation Systems were created)

### Collaborative Filtering 

Intuitive approach that actually does not require Machine Learning to be implemented, but still produces competitive results. The idea of this type of model is to mimic the creation of a sparse matrix Users x Movies, with all the ratings in it, but in a much more efficient way, in the form of dictionaries. From there, through cosine distances, weights can be used to calculate the influence of the opinions of other users to predict the expected rating of a movie from a certain user. Two approaches are taken in this code: 
* The first is a *User-User* collaborative filtering, where there's a loop for each user with all other users to find the ones with similar taste and finally recommend movies that they seemed to like. 
* The second is a *Item-Item* collaborative filtering, where there's a loop for each movie to find the movies most similar to each other. From there, find the one most similar to the ones the user has rated highly to recommend them.
The second approach has proven to not only be faster, but more accurate. This is due to the fact that usually there are more data from users than from items, so looping through items is faster and each item will have more user information than the other way around.
This code shows how intuitive and powerful this approach is, building basically everything by hand, and finishing up with a fully functional model, capable to easily predict a rating of a movie by a user with decent accuracy.

### Matrix Factorization

<p align="center">
  <img src="https://miro.medium.com/max/988/1*nIVWl2ROaxOY23hHajkTTg.png">
</p>

This method takes use of Dimensionality Reduction in order to create two (or more, depending on the biases used) matrices based on K characteristics of the user/product. Note that these can be automatically generated just by manipulating the ratings, and do not need to be manually obtained, such as defining what are the genres of every movie, their length, main actors, and so on. This way, there is a huge increase in practicality and the results are guaranteed. Most importantly, opposed to Collaborative Filtering, this methods scales really well and it is not unthinkable to do this analysis using all, if not most, of the data.
