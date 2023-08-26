# Automatic categorization of questions
The project consists of creating an auto-tagging system for StackOverflow users by automatically suggest tags from the title and the body of the user question. We will test multiple machine learning techniques and train them on more than 100k SO questions.

The project is divided into four sections:
~~~
1- First is the cleaning of the data.
    I started by importing the data from Brazilian E-Commerce Public Dataset by Olist hosted at kaggle website https://www.kaggle.com/olistbr/brazilian-ecommerce. The Data Schema, and the definition of the variables can be found there as well.
    Then, I cleaned the data by:
    - removing not delivered purchases and purchase with missing payed amount
    - removing purchase identified as outlier in terms of payed amount, number of products purchased
    - removing customers identified as outlier in terms of number of purchases made
2- Second we do feature engineering by creating:
    - Recency (time since last order), frequency (number of purchase), and monetary (mean amount payed per purchase) for each customer
    - Delivery Time related to the mean time between the purchase date and the delivery date
    - Review Score related to the mean review score left by the customer
3- Third we analyse the selected features:
    - univariate analysis of each feature
    - bivariate analysis to check for correlation between the features
    - multivariate analysis using t-SNE for three different set/combination of features
        - standardizing the data
        - t-SNE on RFM features
        - t-SNE on RFM features with review score
        - t-SNE on RFM features with review score and delivery time
4- Fourth, clustering of the customers for three different set/combination of features using unsupervised machine learning technique:
    - standardizing the data
    - usage of unsupervised machine learning models (K-means, DBScan, or AgglomerativeHierarchicalClustering)
    - optimizing of the models parameters using silhouette coefficient, elbow curve (for K-means), Davies Bouldin score, NearestNeighbors (for DBScan), and dendrogram (for AgglomerativeHierarchicalClustering) in order to select the optimal number of clusters (for K-means and AgglomerativeHierarchicalClustering), and eps score and min_smaples (for DBScan)
    - do the procedure three times using three different set/combination of features:
        - RFM features
        - RFM features with review score
        - RFM features with review score and delivery time
5- Fifth, performing temporal stability of the clustering using the Adjusted Rand Score in order to give an estimate of updating time for the remodelisation
~~~

The first, second, third, and fourth points are covered in the notebook 'Exploration_notebook'.\
The fourth point is covered in the notebook 'Tesing_notebook'.\
The fifth point is covered in the notebook 'Simulation_notebook'.\
A powerpoint presentation of the project can be shared under request.
