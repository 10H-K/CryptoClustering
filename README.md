# Cryptocurrency Clustering: Unveiling Insights with PCA and K-means #


## Overview ##

This project explores the optimization of cryptocurrency clustering. Initially, the optimal value for k is determined using the original data, employing the elbow method and visualizations to identify the most suitable value. Subsequently, the cryptocurrencies are clustered using K-means based on the original data, and the results are visualized using hvPlot. Following this, the analysis is enhanced through Principal Component Analysis (PCA) to reduce feature dimensionality. The best value for k is then re-evaluated using PCA data, and cryptocurrencies are re-clustered accordingly. Comparisons between the clustering results from the original data and PCA data are visualized and analyzed to understand the impact of using fewer features for clustering. Through these methodologies, insights into the optimal clustering approach and the impact of feature reduction on clustering accuracy are uncovered.


## Process ##

1. Load the Data
    - Load the crypto_market_data.csv into a DataFrame
    - Get the summary statistics and plot the data to see what the data looks like before proceeding
2. Prepare the Data
    - Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file
    - Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame
3. Find the Best Value for k Using the Original Scaled DataFrame
    - Use the elbow method to find the best value for k using the following steps:
      - Create a list with the number of k values from 1 to 11
      - Create an empty list to store the inertia values
      - Create a for loop to compute the inertia with each possible value of k
      - Create a dictionary with the data to plot the elbow curve
      - Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k
4. Cluster Cryptocurrencies with K-means Using the Original Scaled Data
    - Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:
      - Initialize the K-means model with the best value for k
      - Fit the K-means model using the original scaled DataFrame
      - Predict the clusters to group the cryptocurrencies using the original scaled DataFrame
      - Create a copy of the original data and add a new column with the predicted clusters
      - Create a scatter plot using hvPlot as follows
        - Set the x-axis as "PC1" and the y-axis as "PC2"
        - Color the graph points with the labels found using K-means
        - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point
5. Optimize Clusters with Principal Component Analysis
    - Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components
    - Retrieve the explained variance to determine how much information can be attributed to each principal component
    - Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame
6. Find the Best Value for k Using the PCA Data
    - Use the elbow method on the PCA data to find the best value for k using the following steps:
      - Create a list with the number of k-values from 1 to 11
      - Create an empty list to store the inertia values
      - Create a for loop to compute the inertia with each possible value of k
      - Create a dictionary with the data to plot the Elbow curve
      - Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k
7. Cluster Cryptocurrencies with K-means Using the PCA Data
    - Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
      - Initialize the K-means model with the best value for k
      - Fit the K-means model using the PCA data
      - Predict the clusters to group the cryptocurrencies using the PCA data
      - Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters
      - Create a scatter plot using hvPlot as follows:
        - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d"
        - Color the graph points with the labels found using K-means
        - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point
       

## Results ##

![image](https://github.com/10H-K/Crypto_Clustering/assets/152930492/291a4b31-9adc-4091-9143-ec0584056727)

![image](https://github.com/10H-K/Crypto_Clustering/assets/152930492/d38412f5-fc40-46ac-931f-a26590168a76)

![image](https://github.com/10H-K/Crypto_Clustering/assets/152930492/0d97a549-d70b-404c-aebb-fcd123b6dde1)

![image](https://github.com/10H-K/Crypto_Clustering/assets/152930492/91e93464-609e-4f82-9a1d-250c8b987fcd)

![image](https://github.com/10H-K/Crypto_Clustering/assets/152930492/f34e68f6-89be-4cb1-b3c7-8d5b65efce52)
