# Netflix-movies-and-tv-shows_clustering

![N](https://user-images.githubusercontent.com/109894515/206646493-0092c3b0-5fa5-4dbd-a295-07a4f9528fb7.jpg)

Netflix movies and TV shows based on a user's favorite movie or TV show. It uses a a K-Means Clustering model to make these recommendations. These models use information about movies and TV shows such as their plot descriptions and genres to make suggestions.


Netflix, the world’s largest on-demand internet streaming media and online DVD movie rental service provider.it Founded August 29, 1997, in Los Gatos, California by Marc and Reed. It has 69 million members in over 60 countries enjoying more than 100 million hours of TV shows and movies per day Netflix is the world’s leading internet entertainment service with enjoying TV series, documentaries, and feature films across a wide variety of genres and languages. I was curious to analyze the content released in Netflix platform which led me to create these simple, interactive, and exciting visualizations and find similar groups of people.

## **📖Problem Statement**
The goal of this project is to find similarity within groups of people to build a movie recommendation system for users. We are going to analyze a dataset from the Netflix database to explore the characteristics that people share in movies. We have experienced it ourselves or have been in the room, the endless scrolling of selecting what to watch. Users spend more time deciding what to watch than watching their movie.

## **📖Data Summary**
This dataset consists of tv shows and movies available on Netflix as of 2019. The dataset is collected from Fixable which is a third-party Netflix search engine. In 2018, they released an interesting report which shows that the number of TV shows on Netflix has nearly tripled since 2010. The streaming service’s number of movies has decreased by more than 2,000 titles since 2010, while its number of TV shows has nearly tripled. It will be interesting to explore what all other insights can be obtained from the same dataset. Integrating this dataset with other external datasets such as IMDB ratings, rotten tomatoes can also provide many interesting findings.

   #### show_id : Unique ID for every Movie / Tv Show
    
  ####   type : Identifier - A Movie or TV Show
    
   #### title : Title of the Movie / Tv Show
    
   #### director : Director of the Movie
    
   #### cast : Actors involved in the movie / show
    
   #### country : Country where the movie / show was produced
    
   #### date_added : Date it was added on Netflix
    
   #### release_year : Actual Release Year of the movie / show
    
  ####  rating : TV Rating of the movie / show
    
  ####  duration : Total Duration - in minutes or number of seasons
    
  ####  listed_in : Genere
    
  ####  description: The Summary description
  
## Steps involved:

The full code for this article can be found here. It is implemented in Python and different clustering algorithms are used. Below is a brief description of the general approach that I employed:

Data cleaning and pre-processing: Here I checked and dealt with missing and duplicate variables from the data set as these can grossly affect the performance of different machine learning algorithms (many algorithms do not tolerate missing data).
    
 Exploratory Data Analysis: Here I wanted to gain important statistical insights from the data and the things that I checked for were the distributions of the different attributes, correlations of the attributes with each other and the target variable and I calculated important odds and proportions for the categorical attributes.
    
Clustering: Clustering or cluster analysis is a machine learning technique, which groups the unlabelled dataset. It can be defined as "A way of grouping the data points into different clusters, consisting of similar data points. The objects with the possible similarities remain in a group that has less or no similarities with another group." It does it by finding some similar patterns in the unlabelled dataset such as shape, size, colour, behaviour, etc., and divides them as per the presence and absence of those similar patterns. It is an unsupervised learning method; hence no supervision is provided to the algorithm, and it deals with the unlabeled dataset. After applying this clustering technique, each cluster or group is provided with a cluster-ID. ML systems can use this id to simplify the processing of large and complex datasets.

## Conclusion :

*  In this project, we worked on a text clustering problem wherein we had to classify/group the Netflix shows into certain clusters such that the shows within a cluster are similar to each other and the shows in different clusters are dissimilar to each other. The dataset contained about 7787 records, and 11 attributes. 

* Missing values and duplicate values were handled adequately (features like Director was having around 30% cast:9.22 ,country: 6.51% of missing values.)

* Outlier detection and removal techniques were performed to, on date added and released date feature which are kind corelated feature( 61 outliers removed from date_added feature)

*  We began by dealing with the dataset's missing values and doing exploratory 
data analysis (EDA) and found various insights including:


*   In our dataset we have around 69% content as movies, Remaining 31% as TV shows, this signifies people generally prefer movies over TV-Shows.
*	Most content on Netflix is rated for Mature Audiences and over 14 years old.
*	Documentaries  is the topmost genre available on Netflix, followed by Stand-up and Drama
*	From year 2015 there was a significant rise in the rate of making of TV -shows but in 2021 this trend discontinued due to pandemic situation by covid-19 and further the data is not available. 
*	Most vital & Popular words recapitulated in TV-shows and movies are ‘Love', 'Christmas', 'World', 'Story', 'Man', 'Live', 'Girl', 'Life’ this means mostly movies and TV-Shows contains content related to these keywords.
*	Top countries with most number of TV-Shows are 
1.	USA – Not highest in population but the highest content Creator
2.	India
3.	UK
4.	Japan
5.	South Korea


##### ---------------------------Conclusion on Modeling-----------------------------
*     In this project, we worked on a text clustering problem wherein we had to   classify/group the Netflix shows and movies into certain clusters such that the shows and Clusters within a cluster are similar to each other and the shows in different clusters are dissimilar to each other.

*  It was found that Netflix hosts more movies than TV shows on its platform, and the total number of shows added on Netflix is growing exponentially. Also, majority of the shows were produced in the United States, and the majority of the shows on Netflix were created for adults and young adults age group.  

*  It was decided to cluster the data based on the attributes: director, cast, country, genre, and description. The values in these attributes were tokenized, pre-processed, and then vectorized using TFIDF vectorizer. 

*  Through TF-IDF Vectorization, we created a total of 20000 attributes.
    
*    We used Principal Component Analysis (PCA) to handle the curse of dimensionality. 3000 components were able to capture more than around 90% of variance, and hence, the number of components were restricted to 3000. 

*  We first built clusters using the k-means clustering algorithm, and the optimal number of clusters came out to be 10 with good WCSS Value and high silhoutte score of 0.0483. This was obtained through the elbow method and Silhouette score analysis. 

*  Then clusters were built using the Agglomerative clustering algorithm, and the optimal number of clusters came out to be 20 at distance 20. This was obtained after visualizing the dendogram.  

* DBSCAN cluster didn't gave satisfying results. it was a kind of biased model which was clustering most of the data into a single cluster.
Estimated number of clusters: 19  
Estimated number of noise points: 7134

* Build a SVM Classification model with hyperparamater tuning at the end to predict a cluster number for a data record.

* Classifier predicts good result with above 99% accuracy.
