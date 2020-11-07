# Table of Contents

* [Summary](#summary)
* [Unsupervised Learning](#unsupervised-learning)
  * [Hierarchical Agglomerative Clustering](#hierarchical-agglomerative-clustering)
    * [Visualizations](#visualizations)
    * [Results](#results)
  * [K-means Clustering](#k-means-clustering)

# Summary

We are making use of a [Spotify dataset](https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks) consisting of 160,000 songs ranging from the years 1921 to 2020 in order to understand and interpret what numerical features make a song popular and how the definition of these numerical features has changed over time.

# Unsupervised Learning

## Hierarchical Agglomerative Clustering

### Visualizations

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
