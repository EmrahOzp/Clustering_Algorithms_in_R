# Clustering_Algorithms_in_R
Clustering Algorithms in R

Clustering is similar to classification but the basis is different. 
In clustering we don’t now what we are looking for and we are trying to identify some segments or clusters in our data. 
While using clustering algorithms on our dataset, we should expect structures, clusters and groupings to pop up.  
There are two important machine learning clustering algorithms.

	K-Means Clustering
	Hierarchical Clustering


K-MEANS CLUSTERING 
It is a very convenient tool to discovering groups and categories inside our data. 

	Choose the number K of clusters
	Select at random K points, the centroids (not necessarily from the dataset)
	Assign each data point to the closest centroid  that forms K clusters
	Compute and place the new centroid of each cluster
	Re-assign each data point to the new closest centroid. If any reassignment took place,
go to the previous step otherwise finish your model.

! – Random initialization trap; initial selection of the centroids may effect the outcome of the clustering process and 
solution is “k-means ++ algorithm” . Python and R have special functions to tackle this issue. 

! – Choosing the right number of clusters; we perform a WCSS (Within Cluster sum of Squares) algorithm to choose the
optimum number of clusters. Which is taking sum of squared distances of each point with respect to the centroids. 
As we increase the number of clusters the distance between points and centroids will decrease so does the WCSS.
But, this is a constantly decreasing metric, WCSS would reach zero as number of clusters reach number od data points.
Therefore to find the optimal point we use the “Elbow Method” which is a comparison of marginal effect between 
number of clusters vs. WCSS. 

DATA SET + BUSINESS PROBLEM DESCRIPTION
This dataset contains information about a shopping mall in a specific city in which clients subscribe a membership card. 
While they subscribing they provide information about their “Gender”, “age”, “Annual Income”. 
As they use this card while they are shopping around a “purchases score card has been generated” based on their income
and number of times they shopped. The score matrix contains values from 1 to 100. Closer to 1, client spends less, and closer to 100,
client spends the most. Our objective is to define classes/segments based on annual income and spending score. 
It is a clustering problem because we do not know how many segments are available in the dataset.   

HIERARCHICAL CLUSTERING 
Different process than K-Means. There are two types of hierarchical clustering. Agglomerative (a bottom up approach) and 
Divisive (starting from top and dividing the dataset).

Agglomerative HC:
	Make each data point a single-point cluster , which forms N clusters. 
	Take the two closest data points and make them one cluster, That forms N-1 clusters.
	Take the two closest clusters and make them one cluster, that forms N-2 clusters.
	Repeat the previous step until there is only one cluster. 

! – The closest clusters are determined by using Euclidean Distances. 
! – It is a crucial element how you define your measuring method between the clusters, which may affect your algorithm. 

You may measure the distances between clusters by using;
	Closest points
	Furthest Points
	Average Distance
	Distance between centroids

By repeating the above procedure we develop a “dendogram” which indicates us to choose the optimum number of clusters 
by defining the similarity threshold (highest vertical distance which does not cross the horizontal lines).
Similar to the “elbow” method. Dendogram contains the memory of hierarchical clustering.   
