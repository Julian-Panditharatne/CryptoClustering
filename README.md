# **Crypto Clustering Challenge**

In this challenge, I used Python - mostly Pandas, SciKit Learn, and hvPlot - along with unsupervised learning knowledge and techniques to predict if cryptocurrencies are affected by 24-hour or 7-day price changes. This was done in the following manner:

## Prepared the Data

- Used the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
- Created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Found the Best Value for `k` by using the Original Data

Use the elbow method to find the best value for `k` using the following steps:

- Created a dictionary with a list of `k` values from 1 to 10 as one entry and a list inertia values for each `k` value as the other entry to plot the elbow curve.
- Plotted a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.

## Clustered the Cryptocurrencies with K-Means by using the Original Data

Used the following steps to cluster the cryptocurrencies for the best value for `k` on the original scaled data:

- Initialized the K-means model with the best value for `k`.
- Fitted the K-means model using the original scaled DataFrame.
- Predicted the clusters to group the cryptocurrencies using the original scaled DataFrame.
- Created a copy of the original data and added a new column with the predicted clusters.
- Created a scatter plot using hvPlot as follows:
  - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
  - Colored the graph points with the labels found using K-means.
  - Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

## Optimized the Clusters with Principal Component Analysis

- Using the original scaled DataFrame, performed a PCA and reduced the features to three principal components.
- Retrieved the explained variance to determine how much information can be attributed to each principal component.
- Created a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Found the Best Value for `k` by using the PCA Data

Used the elbow method on the PCA data to find the best value for `k` using the following steps:

- Created a dictionary with a list of `k` values from 1 to 10 as one entry and a list inertia values for each `k` value as the other entry to plot the elbow curve.
- Plotted a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.

## Clustering the Cryptocurrencies with K-means by using the PCA Data

Used the following steps to cluster the cryptocurrencies for the best value for `k` on the PCA data:

- Initialized the K-means model with the best value for `k`.
- Fitted the K-means model using the PCA data.
- Predicted the clusters to group the cryptocurrencies using the PCA data.
- Created a copy of the DataFrame with the PCA data and added a new column to store the predicted clusters.
- Created a scatter plot using hvPlot as follows:
  - Set the x-axis as "PCA1" and the y-axis as "PCA2".
  - Colored the graph points with the labels found using K-means.
  - Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

## Visualizing and Comparing the Results

- Created a composite plot by using hvPlot and the plus sign (+) operator to compare the elbow curve created from the original data with the one created from the PCA data.
- Created a composite plot by using hvPlot and the plus (+) operator to compare the cryptocurrency clusters that resulted from using the original data with those that resulted from the PCA data.

---

## **Repository Files and Folders**

Besides this `README.md` file, there are three files and one folder.

Two of those files are outside of the folder and are within the root directory alongside the `README.md` file:

- `Crypto_Clustering.ipynb`: The Jupyter Notebook file containing the script used to perform the unsupervised learning techniques.
- `Crypto_Clustering_starter_code.ipynb`: The Jupyter Notebook file containing the starter code used to make the script in `Crypto_Clustering.ipynb`.

Within the folder, which is named ***Resources***, there is the CSV file named `crypto_market_data.csv` that contains the data used for this challenge.

---

## **References**

Holoviz contributors. (2023). *Composing Plots — HoloViz 0.17.3 documentation*. Holoviz.org. <https://holoviz.org/tutorial/Composing_Plots.html#composing-plots>

scikit-Learn. (n.d.). *Glossary of Common Terms and API Elements — scikit-learn 0.24.2 documentation*. Scikit-Learn.org. <https://scikit-learn.org/stable/glossary.html#term-random_state>

scikit-Learn. (2010). *2.3. Clustering — scikit-learn 0.20.3 documentation*. Scikit-Learn.org. <https://scikit-learn.org/stable/modules/clustering.html#k-means>

scikit-Learn. (2024). *KMeans*. Scikit-Learn. <https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html#kmeans>
