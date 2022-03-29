# Cryptocurrencies

## Overview of the analysis:

Marta has a chance to pitch an investment in cryptocurrencies to her firm, Accountability Accounting, and we have agreed to help her out. There are many more cryptocurrencies that are more affordable than Bitcoin on the market.
Marta has a dataset of cryptocurrencies and we can analyze it anyway we want. Our goal is to help Marta discover trends using unsupervised machine learning, that will convince her firm to invest in new cryptocurrencies.

The data presented is not clean, therefore it needed to be processed to fit the machine learning models using unsupervised learning as there is no known output as to what we are looking for in terms of results.
Unsupervised learning was used to process data, cluster, reduce dimensions, and reduce the principal components of PCA, to present our findings.

## Results:

The code for the unsupervised machine learning algorithms can be found in the jupyter notebook file [crypto_clustering](https://github.com/Cryptotwister/Cryptocurrencies/blob/main/crypto_clustering.ipynb).

### Deliverable 1: Preprocessing the Data for PCA

* The data is loaded from [crypto_data.csv](https://github.com/Cryptotwister/Cryptocurrencies/blob/main/Resources/crypto_data.csv).

![Deliverable 1 - Data loaded](https://user-images.githubusercontent.com/42978221/160651989-5bfd2739-c895-4dee-a651-8c4d628d4793.png)

* Only traded cryptocurrencies are being kept;
* Only cryptocurrencies that have a working algorithm are being kept;
* The "IsTrading" column is removed;
* All rows that have at least 1 null value are removed;
* A new DataFrame that holds only the cryptocurrencies names created;
* The 'CoinName' column is removed;
* Get_dummies() method used to create variables for text features;
* The data is standardized with StandardScaler().

![Deliverable 1 - Data drop, dummies, stanandardized](https://user-images.githubusercontent.com/42978221/160661811-91bc7c94-22ea-45d8-b1d4-0ee9d21a5df3.png)

### Deliverable 2: Reducing Data Dimensions Using PCA

* The PCA algorithm is used to reduce dimensions of the X DataFrame down to three principal components.

![Deliverable 2 - Reducing data (PCA)](https://user-images.githubusercontent.com/42978221/160662503-c925898f-2269-4351-a8b9-80a56bbb84fa.png)

### Deliverable 3: Clustering Cryptocurrencies Using K-Means

* The K-means algorithm is used to cluster the cryptocurrencies:

![Deliverable 3 - Clustering](https://user-images.githubusercontent.com/42978221/160664406-13214ffa-e282-4469-a676-f2d3b6b91382.png)

### Deliverable 4: Visualizing Cryptocurrencies Results

![Deliverable 4 - 3D-Scatter with Clusters](https://user-images.githubusercontent.com/42978221/160666279-2b2e6b60-6870-4e3e-b9e7-ccb7f2d59a9e.png)

* A table with tradable cryptocurrencies (532 total) is created.

![Deliverable 4 - Table with tradable cryptocurrencies (532)](https://user-images.githubusercontent.com/42978221/160666742-6361e1a6-d804-4bb6-80c5-cb545e769a4f.png)

* A new DataFrame is created that has the scaled data with the clustered_df DataFrame index and added 'CoinName' and 'Class' columns.

![Deliverable 4 - new DF + scatter plot](https://user-images.githubusercontent.com/42978221/160667977-88566c82-49e6-47e1-b247-765acd351793.png)

* A hvplot scatter plot is created where the X-axis is "TotalCoinsMined" and "TotalCoinSupply" is the Y-axis.
