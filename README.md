# Optimal Number of Components in PCA (Principal Component Analysis)
Running a machine learning algorithm on a dataset, with very higher number of features not only requires high computational power but also is very time consuming. Can we reduce dimensions of our dataset by ignoring some componets of data ? If yes, what is the optimal number of componets, we should use without loosing significant algorithmic accuracy. **This project implements a statistical approach to decide number of Components in Principal Component Analysis, using Explained-Variance.**
</br></br>
**Refer to the [jupyter notebook](https://github.com/Jigyansu-Nanda/Number-of-Components-in-PCA/blob/master/Deciding%20number%20of%20Components%20in%20PCA.ipynb) for implementation and logic behind the approach.**

## Principal Component Analysis
Say, we have a d-dimensional (large value of d) dataset. Running an ML algorithm on so many features will require high computational power and will consume a lot of time. But if we have redundant features on the dataset, we can simply drop one of those features without sacrificing significant algorithmic accuracy and retaining most of the information. Hence we reduce d-dimensions into k-dimensions based dataset. **(where k < d)**. The approach is as follows:
  - Normalize the intial dataset
  - Find the corresponding Eigenectors and Eigenvalues from the covariance matrix or correlation matrix
  - Sort the obtained Eigenvalues in descending order
  - For k Eigenvalues from the beginning, we choose their corresponding k number of Eigenvectors
  - Create a projection matrix from these k Eigenvectors
  - Create a new k-dimensional dataset using the above created projection matrix
  
## Deciding optimal value of K
We will use a measure called **Explained Variance**. The Explained Variance tells us how much information (variance) can be attributed to each of the principal components. Looking at cumulative values of Explained varinace associated with each component, we can decide which features, we can drop out safely.

