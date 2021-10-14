# Cryptocurrencies
Unsupervised Machine Learning on cryptocurrency data using a clustering algorithm

## Project Overvievw
The purpose of this project was to demonstrate Principal Component Analysis (PCA), clustering using K-means algorithm, and plotting of results using hvplot and plotly on cryptocurrency dataset. Findings can be used to group cryptocurrencies for the purpose of an investment classification system.

### Resources
- Data Source: [crypto_data.csv](https://github.com/samanthajpv/Cryptocurrencies/blob/72b1bb7b7443f070044c3dfcfe424bcf82028944/crypto_data.csv) from https://min-api.cryptocompare.com/data/all/coinlist
- Language: Python 3.7.10
    - Libraries: pandas, scikit-learn, plotly, hvplot
- Software: Jupyter Notebook
- Code: [crypto_clustering.ipynb](https://github.com/samanthajpv/Cryptocurrencies/blob/main/crypto_clustering.ipynb)

## Method
**A. Preprocessing the Data for PCA**

Data preprocessing is a crucial step to prepare the data for Principal Component Analysis (PCA). This process includes selecting/filtering and organizing data by formatting, cleaning (e.g. removing rows with null values, dropping columns not needed), and scaling features.

**B. Reducing Data Dimensions Using PCA**

With the scaled features, PCA was performed to reduce data dimension to three principal components. A dataframe was then created with the three principal components which were used in the clustering.

**C. Clustering Cryptocurrencies Using K-means**

An elbow curve was created from the dataframe produced in the PCA to get the best value for k. As seen in the figure below, 4 was chosen as the k value. This was plugged as the number of clusters for the K-Means model. The array of predicted clusters was added to a dataframe with the features in preparation for the visualization in the next step.
<p align="middle">
    <img src="https://github.com/samanthajpv/Cryptocurrencies/blob/46e70cc854d5edb5d759ddfb3f7ab3bf7c25e6c5/Images/elbow_curve.png" width="500" height="250"/>
</p>

**D. Visualizing Cryptocurrencies Results**

- Using Plotly Express, a 3D scatter plot was created to visualize the predicted clusters of the principal components. The figure below is able to show the groupings of cryptocurrencies with comparable features.
<p align="middle">
    <img src="https://github.com/samanthajpv/Cryptocurrencies/blob/46e70cc854d5edb5d759ddfb3f7ab3bf7c25e6c5/Images/3d_scatter.png" width="500" height="300"/>
</p>

- With hvPlot, an interactive table was created to list the tradable cryptocurrencies. This table is sortable and selectable.
<p align="middle">
    <img src="https://github.com/samanthajpv/Cryptocurrencies/blob/46e70cc854d5edb5d759ddfb3f7ab3bf7c25e6c5/Images/hvplot_table.png" width="550" height="275"/>
</p>

- Before creating the scatter plot for TotalCoinsMined vs TotalCoinSupply, data was scaled using the MinMaxScaler. The scaled data was added to a dataframe with the CoinName and Class for the scatter plot below. It can be seen that the points are mostly concentrated in one area.
<p align="middle">
    <img src="https://github.com/samanthajpv/Cryptocurrencies/blob/46e70cc854d5edb5d759ddfb3f7ab3bf7c25e6c5/Images/hvplot_scatter.png" width="500" height="250"/>
</p>

## Reference
(1) Trilogy Education Services. (2021, October). *Module 18 Challenge*. https://courses.bootcampspot.com/courses/626/assignments/13354?module_item_id=213799
