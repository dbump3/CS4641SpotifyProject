# Table of Contents

* [Summary](#summary)
* [Unsupervised Learning](#unsupervised-learning)
  * [Hierarchical Agglomerative Clustering](#hierarchical-agglomerative-clustering)
    * [Visualizations](#visualizations)
    * [Results](#results)
  * [K-means Clustering](#k-means-clustering)

# Summary


We are making use of a [Spotify dataset](https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks) consisting of 160,000 songs in order to understand the interesting correlations that exist between a song's popularity and other features such as instrumentalness, speechiness, danceability, etc. We believe that by making use of different visualizations and agglomeration methods, insightful relations might be discovered. Ultimately, our goal is to apply data science and machine learning to better understand what makes a song popular.

# Unsupervised Learning

## Hierarchical Agglomerative Clustering

### Visualizations

The first thing we did after reading the data from the spotify dataset was separate the columns into numerical features and categorical features.

```py
data_num = data[['acousticness', 'danceability', 'duration_ms', 'energy',
       'instrumentalness', 'liveness', 'loudness', 'popularity',
       'speechiness', 'tempo', 'valence', 'year']]
data_cat = data[['explicit', 'mode', 'key']]

```

Then, we plotted the distributions of each numeric feature to get a sense of how each variable is distributed. The following are just some of the generated histograms.

```py
#distributions for all numeric variables 
for i in data_num.columns:
    plt.hist(data_num[i])
    plt.title(i)
    plt.show()
```

<img src="img/num1.png"/>
<img src="img/num2.png"/>
<img src="img/num3.png"/>


To see the correlations that exist between every single numerical feature, we ran the following heatmap, which already displays some interesting relations.



The first thing we did as we approached the problem of clustering our data was to create a heatmap showing the correlation of various features. This would prove useful later when deciding which values to compare on a scatterplot.

#### Correlation of Features
<img src="img/correlation_heatmap.svg"/>

We then decided to try hierarchical clustering considering the simplicity of the data. We created a dendrogram through agglomerative clustering in order to visualize the outlook of the clusters. After looking at the denderogram, we decided on decisive clustering with 2 clusters.

#### Dendrogram
<img src="img/dendrogram.svg"/>

In the last visualization, we created a scatterplot of the loudness and duration in milliseconds of the songs after clustering. 

#### Loudness v. Duration (ms) after Clustering
<img src="img/hac_clustering.svg"/>

### Results

The result of the hierarchical agglomerative clustering with 2 clusters is 2 clear groups: a cluster with small duration and a large range of loudness and a cluster with long duration and a slightly smaller range of loudness that is, on average, louder.

## K-means Clustering

TODO
