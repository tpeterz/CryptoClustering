# CryptoClustering

# Module 11 Challenge 
# MSU AI Bootcamp 2023 - 2024
## Author:
- Taylor Peterson
# Description
>In this Challenge, you’ll apply your understanding of the K-means algorithm and principal component analysis (PCA) to classify cryptocurrencies according to their price fluctuations across various timeframes. Specifically, you will examine price changes over intervals spanning 24 hours, 7 days, 30 days, 60 days, 200 days, and 1 year.

# 1. Prepare the Data
* Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
* Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
    * The first five rows of the scaled DataFrame should appear accurately. 

# 2. Find the Best Value for k Using the Original Scaled DataFrame
Use the elbow method to find the best value for k by completing the following steps:

* Create a list with the number of k values from 1 to 11.
* Create an empty list to store the inertia values.
* Create a for loop to compute the inertia with each possible value of k.
* Create a dictionary with the data to plot the elbow curve.
* Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
* Answer the following question in your notebook: What is the best value for k?

# 3. Cluster Cryptocurrencies with K-Means Using the Original Scaled Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

* Initialize the K-means model with the best value for k.
* Create an instance of K-means, define the number of clusters based on the best value of k, and then fit the model using the original scaled DataFrame.
* Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
* Create a copy of the original data and add a new column with the predicted clusters.
* Create a scatterplot using pandas’ plot as follows:
    * Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".

# 4. Optimize Clusters with Principal Component Analysis
* Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
* Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
    * What is the total explained variance of the three principal components?
* Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
    * The first five rows of the PCA DataFrame should appear accurately.

# 5. Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k using the following steps:

* Create a list with the number of k-values from 1 to 11.
* Create an empty list to store the inertia values.
* Create a for loop to compute the inertia with each possible value of k.
* Create a dictionary with the data to plot the elbow curve.
* Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
* Answer the following questions in your notebook:
    * What is the best value for k when using the PCA data?
    * Does it differ from the best k-value found using the original data?

# 6. Cluster Cryptocurrencies with K-Means Using the PCA Data
Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

* Initialize the K-means model with the best value for k.
* Create an instance of K-means, define the number of clusters based on the best value of k, and then fit the model using the PCA data.
* Predict the clusters to group the cryptocurrencies using the PCA data.
* Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
* Create a scatte rplot using pandas’ plot as follows:
    * Set the x-axis as "PC1" and the y-axis as "PC2".
* Answer the following question:
    * What is the impact of using fewer features to cluster the data using K-Means?

# 7. Determine the Weights of Each Feature on Each Principal Component
* Create a DataFrame that shows the weights of each feature (column) for each principal component by using the columns from the original scaled DataFrame as the index.
* Which features have the strongest positive or negative influence on each component?

# Submission and Grading Requirements:
## Coding Conventions and Formatting 
To receive all points, you must:

* Place imports at the top of the file, just after any module comments and docstrings, and before module globals and constants. 

* Name functions and variables with lowercase characters, with words separated by underscores. 

* Follow DRY (Don't Repeat Yourself) principles, creating maintainable and reusable code. 

* Use concise logic and creative engineering where possible. 

## Deployment and Submission 
To receive all points, you must:

* Submit a link to a GitHub repository that’s cloned to your local machine and that contains your files. 

* Use the command line to add your files to the repository. 

* Include appropriate commit messages in your files. 

## Code Comments 
To receive all points, your code must:

* Be well commented with concise, relevant notes that other developers can understand.
# References
1. 