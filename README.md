# velib-clustering
A clustering process on Velib data. Velib are the bike stations in Paris. The data set contains usage data on 1189 stations.

# Objective
The idea is to cluster the stations regarding its usage data. 

# Data set
The data set contains the usage of Velib stations from Sunday 31st of August to the Sunday 7th of September of 2014.
The data available is explaining the usage of each station by the station's capacity from 0 to 1. If the station is full of bikes the capacity is 1, if they are empty the capacity is 0.
Here an example of the capacity on station number 19117.

![station-cap](/assets/station-19117.png)

We also have the Latitue and Longitude of each bike station.

# Results and Discussion
We have used PCA to reduce the dimension to two main components that explain almost half of the information and to obtain a visualization. We observed that with 19 components we could explain 90% of the information contained in the hourly bike use.

We have used HC and k-means to cluster 4 groups depending on the loads of the bike stations. The selection of the clustering is done by screeplotting and observing the best place to cut the HC tree.
We have combined the clustering with PCA to show the effect of each variable on the clustering. We have modified the biplot graph to better show the relationship between variables and clustering attribution.

![pca-circle](/assets/pca-circle.png)

We have plotted the cluster means (mean average capacity) of each bike station to better understand its usage during a week.

![4-cluster-means](/assets/4-cluster-means.png)

When plotting the cluster means we observe that on:

- *cluster 1*: During the **week days** the stations are full at noon during the week days, this means that the stations are close to **business district**. The stations are empty at midnight. During the **weekend** the use is less abrupt. We can identify it in the map as the **city center** in `red`.

- *cluster 2*: During **week days**, it can be seen as the opposite of cluster 1. They are full at midnight and empty at noon, people leave their houses in the morning and start taking bikes. In the evening they come back home and the bike stations start to fill up. We can identify it in the map as the **residential areas** in `orange`.
During the **weekend** the peaks are delayed as people come back home late at night.

- *cluster 3*: the stations are most of the time full with peaks at midnight and valleys at noon. They follow the *cluster 2* trend and its trend is steady even during the weekends. This means that this cluster is a **mix of a residential area and a commercial area** in `cyan`.

- *cluster 4*: the stations are most of the time empty, so we can say that these stations are rarely refilled and mostly refilled in the morning very soon, from midnight to 6 am. During the weekends they are mostly empty. This behaviour invites to think that these stations are mostly for consuming bikes and rarely as destination and they are refilled very soon in the morning, probably by Velib workers. You can find them in `dark blue` on the map.

The map of the Velib stations with its clustering is as follows:

![4-clusters-map](/assets/4-cluster-map.PNG)
