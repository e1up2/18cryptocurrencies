# Cryptocurrencies
## Overview
In this project, we use unsupervised learning to discover patterns and groups in a cryptocurrency dataset that will help determine what class of cryptocurrencies are tradable. In the initial phase, we process the dataset for input into the machine learning algorithm; then, we group the data using the clustering and K-Means algorithms. Finally, we would make our model more efficient by using the Principal Component Analysis.

### Control Flow
1. Basic Data Processing
    - Read in dataset
    - Keep cryptocurrencies that are traded
    - Keep cryptocurrencies that have a working algorithm
    - Remove rows that have at least one null value
    - Keep rows where cryptocurrencies are mined
2. Data Processing for PCA
    - Create a new DataFrame that holds only the cryptocurrencies names
    - Drop the 'CoinName' column since it's not going to be used on the clustering algorithm.
    - Use get_dummies() to create variables for text features
    - Standardize the data with StandardScaler()
 3. Reducing Data Dimensions Using PCA
    - Use PCA to reduce dimension to three principal components
    - Create a DataFrame with the three principal components.
4. Clustering Crytocurrencies Using K-Means
    - Create an elbow curve to find the best value for K and calculate the inertia for the range of K values
    - Create the elbow curve
    - Run K-Means with K=4
    - Create a new DataFrame including predicted clusters and cryptocurrencies features
5. Visualizing Cryptocurrencies Results
    - Creating a 3D-Scatter with the PCA data and the clusters
    - Create a table with tradable cryptocurrencies.
    - Scale the data to create the scatter plot with tradable cryptocurrencies
    - Create a new DataFrame that has the scaled data with the clustered_df DataFrame index
    - Create a hvplot.scatter plot using x="TotalCoinsMined" and y="TotalCoinSupply".


## Results
##### One-Hot Encoding
![One_Hot_Encoding](images/one_hot_encoding.png)

##### Principal Component Analysis DataFrame
![PCA_DataFrame](images/pca_df.png)

##### Elbow Curve
![Elbow_Curve](images/elbow_curve.png)

##### 3D-Scatter with the PCA data and the clusters
![3D_Scatter](images/3D_scatter.png)

##### Hvplot Table with tradable cryptocurrencies
![Hvplot_Table](images/hvplot_table.png)

##### Hvplot Scatter plot using x="TotalCoinsMined" and y="TotalCoinSupply".
![Hvplot_Scatter](images/hvplot_scatter.png)


### Summary
After initial data processing, converting text features to dummy variables, and standardizing the crypto dataset with StandardScaler(), we can reduce the data dimensions to three components using PCA.
Our elbow curve determined that our optimal number of clusters is K=4. Using K=4, we create four clusters. We notice that one of the clusters has only one cryptocurrency. We may further evaluate this data point to determine if we can drop that data point.

Finally, we create a hvplot table showing our final cryptocurrencies and their classes and a 2D-scatter plot showing TotalCoinedMined and TotalCoinsSupplied.
Similar to the 3D-Scatter plot, our 2D-Scatter plot shows that we have one outlier cryptocurrency.
