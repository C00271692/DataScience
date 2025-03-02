1. Setting up for K-Means Clustering, whihc is a similar enough algorithm to KNN which i done previously.

2.  Similar setup, reducing rows for easier computation

3. Only using numeric data for KMC, so dropping categorical cols

4. Set up pre-process pipeline, again same to previous KNN (Fill missing values with the mean (average) of that column, Standardize the features by removing the mean and scaling to unit variance)

5. Define nmber of clusters

6. Using PCA we effectively reduce our muti dimensioned data, into 2D which can be thrown into a graph

7. 