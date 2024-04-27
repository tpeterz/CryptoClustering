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
    #### **Answer**: 
    >The best value for `k` would be 4, the curve begins to flatten there.

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
    #### **Answer**:
    >#### Principal Component 1 (PCA1): 0.3719856
    >#### Principal Component 2 (PCA2): 0.34700813
    >#### Principal Component 3 (PCA3): 0.17603793
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
    #### **Answer**: 
    >It appears that at k=4, or 4 clusters, the elbow curve starts to straighten. The graph moves rapidly at this point and, visually, it appears to be a the "bend" in the elbow displayed.
    * Does it differ from the best k-value found using the original data?
    #### **Answer**: 
    >I am not sure if it is supposed to differ, as I had previously determined the same number of clusters. So, it did not change using PCA data. 

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
    #### **Answer**: 
    >By using fewer features to cluster the data using K-means, it can display more defined cluster groups, especially when plotting. By adding more clusters for this model to handle, it reduces variability and can lead to overfitting. By using fewer, but not too few (as the result would show signs of underfitting), I can get a clear view of cluster groups when plotting my data with a scatter plot (using colors as an added reference/disguishment). (Ref: #5)

# 7. Determine the Weights of Each Feature on Each Principal Component
* Create a DataFrame that shows the weights of each feature (column) for each principal component by using the columns from the original scaled DataFrame as the index.
* Which features have the strongest positive or negative influence on each component?
#### **Answer**:
#### Component #1 - `PCA1`: 
* Both the `price_change_percentage_200d` (0.594468) and `price_change_percentage_1y` (0.568379) features had the strongest **positive influence** on this component. The `price_change_percentage_24h` (-0.416728) had the strongest **negative** influence on this component. This tells me that the price change over longer intervals (200 days and 1 year) have stronger positive influence on this component than price changes over smaller (much smaller, 24-hour) intervals of time, that have negative influence. 

####  Component #2 - `PCA2`:
* Both `price_change_percentage_30d` (0.562182), and `price_change_percentage_14d` (0.540415) features had the strongest **positive** influence on this component. `The price_change_percentage_1y` (-0.150789) feature had the strongest **negative** influence on this component, although not by much. This tells me that a "medium" interval of time for price changes would have the strongest positive impact. The two highest intervals of time, `price_change_percentage_200d`(200 days) and `price_change_percentage_1y` (1 year), display scores very close to zero, meaning they have very little influence on this component.

####  Component # 3 - `PCA3`: 
* The `price_change_percentage_7d` (0.787670) feature had the strongest **positive** influence on this component. It scored much higher than any other feature, compared against any of the 3 components. The `price_change_percentage_60d` (-0.361377) had the **strongest** negative influence on the component. The influence of the features on this component decreases in similar intervals from the price change percentage 14-day feature, to the 60-day feature. It then starts to steadily increase at the 200 day mark, which makes me wonder what it would look like if I had more data and columns that contained features that extended years into the future.  
#### (Ref #1)  

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
1. [Elbow Method for Finding the Optimal Number of Clusters in K-Means](https://www.analyticsvidhya.com/blog/2021/01/in-depth-intuition-of-k-means-clustering-algorithm-in-machine-learning/#:~:text=When%20we%20analyze%20the%20graph,an%20optimal%20number%20of%20clusters.) - used to determine clusters by looking at plots of the 'elbow method'.
2. Module 11, Day 1 Activities - The specific activities will be referenced throughout my code.
3. Module 11, Day 2 Activities - The specific activities will be referenced throughout my code.
4. Module 11, Day 3 Activites - The specific activities will be referenced throughout my code.
5. [K-Means Clustering Explained](https://neptune.ai/blog/k-means-clustering#:~:text=Some%20factors%20can%20challenge%20the,clusters%20can%20result%20in%20overfitting.) - used for determining what happens when more clusters are added to K-means. 