# Hierarchical Clustering for Seed Categorization

## Project’s Objective:

● Implement Hierarchical Clustering on the UCI seed dataset to divide it in groups and
implement KNN to identify the species
● Implement agglomerative clustering and KNN

### Dataset Link:

[https://archive.ics.uci.edu/ml/machine-learning-databases/00236/seeds_dataset.txt](https://archive.ics.uci.edu/ml/machine-learning-databases/00236/seeds_dataset.txt)

## Data

The data directory should contain two csv files:

- `Seed_Data.csv`: The dataset, including given columns

| A | P | C | LK | WK | A_Coef | LKG | Target |
| --- | --- | --- | --- | --- | --- | --- | --- |

## Dataset Columns Descriptions:

To construct the data, seven geometric parameters of wheat kernels were measured:

1. Area A
2. Perimeter P
3. Compactness C = 4*pi*A/P^2
4. Length of kernel
5. Width of kernel
6. Asymmetry coefficient
7. Length of kernel groove
8. 

## Steps (implementation steps are defined in code):

● Grouping the seed dataset into n clusters using hierarchical agglomerative clustering

● Creating new features for the datapoints in the given dataset based on other cluster (using cluster’s centroid) and added them into the existing features of the dataset. Generate new features beased on distance

● Similar procedure is followed for testing dataset

● New features are scaled using min max

● Now, training dataset have extra feature values that is calculated based on similarity
between data points

● Implement KNN classifier on the modified dataset to identify the cluster ids

● Performance of the model on unknown data is measured by the K-fold cross validation method (Dataset is split into k subsets)

● Find the suitable number of clusters for different single linkages, complete linkage, and average linkage

● Make Predictions on unlabeled data

## Code Structure:

**Implement Hierarchical clusterin (agglimerative clustering) model to divide the
training dataset into n clusters**

Class AgglomerativeClustering:

- **init** : Initialization
- **fit_predict :** fit data and predicting labels
- **clustertolabels :** for clusters to labels
- **d_matrix :** distance matrix
- **update_d:** update distance matrix according to linkage
- **updatea_cluster :** merge cluster
- **distance :** distance between two points

**Implement KNN for classification of labels for unlabeled dataset**

def KNN_classification (sample, k, X, y):

- **dist_cartesian :** calculate cartesian distance
- **lbl_classify :** final label
- **KNN_classification :** classification

**Implement k-fold cross validation method for estimating the performance of the
model**

def split_CV(dataset_KNN, folds): Returns the accuracy for each interaction in the range of k folds
def CV_split(dataset, folds): Dataset splits with respect to k-fold

**Code Block for the value of clusters, neighbours, and linkage**

- n_clusters = [3,4,5,6,7]
- knn = [3,5,7,9,11]
- linkages = [‘single’, ‘complete’, ‘average’]

**Code block is used to make predictions on test data**

**Run KNN on given dataset (without adding new features) and find the accuracy**
