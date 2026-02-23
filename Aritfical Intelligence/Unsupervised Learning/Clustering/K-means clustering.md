K-Means clustering is a popular unsupervised machine learning algorithm that partitions unlabeled data into
distinct, non-overlapping subgroups (clusters) based on feature similarity. It iteratively assigns data points to the nearest centroid and updates centroids by calculating the mean of all points in the cluster, aiming to minimize within-cluster variance (sum of squared distances.

To determine the best number of cluster in the k-means clustering we will use the the elbow method which means where we get the elbow point we will choose that point as the number of cluster 

for eg->
![[Pasted image 20260223175716.png]]
so in the above figure we will choose 3 as the number of cluster because it the elbow point


In [K-Means clustering](https://www.geeksforgeeks.org/machine-learning/k-means-clustering-introduction/), the algorithm partitions data into k clusters by minimizing the distances between points and their cluster centroids. However, deciding the ideal k is not straightforward. The Elbow Method helps by plotting the Within-Cluster Sum of Squares (WCSS) against increasing k values and looking for a point where the improvement slows down, this point is called the "elbow."