---
title: "Getting started with Basemap in Python"
collection: blog
permalink: /blog/post_3
excerpt: 'This tutorial introduces the nitty gritties of plotting 2D and 3D data on Geographical Maps by using Matplotlib Basemap toolkit'
date: 2017-01-09
---

You can find the Jupyter Notebook [here](https://github.com/Pulkit-Khandelwal/blogs-notebooks/blob/master/Basemap/Basemap_post_1.ipynb)

This tutorial introduces the nitty gritties of plotting 2D and 3D data on Geographical Maps by using [Matplotlib Basemap toolkit](http://matplotlib.org/basemap/users/intro.html). As part of the term project for Applied Machine Learning course at McGill University in Fall 2016, we were given the task of predicting various behaviours of animal movement aimed at conservation of the species. The data is in the form of time series and can be otained at [movebank](https://www.movebank.org/), which is a repository of animal tracking data accumulated from various scientific studies. My team had chosen to analyze the migratory behaviour of Lesser Black-backed Gulls birds. The reference paper and the data can be found [here](https://www.datarepository.movebank.org/handle/10255/move.494).

This is the first notebook which I have created to walk you through the project. In this notebook, I will get you accustomed to the data and concentrate on plotting the data on a world map. In the posts to follow some data cleansing will be done, we will see in detail what movebank has to offer to the machine learning community in terms of data and literature. I will then briefly talk about the problems we had tackled. We will then walk through some unsupervised learning algorithms and subsequently delve into deeper models.

Before starting with the making pretty plots, take note of some important links:
* You can find the project report, code and any addiotnal links in my [git repo](https://github.com/Pulkit-Khandelwal/COMP551-Applied-Machine-Learning/tree/master/Capstone%20Project).
* I stumbled upon a very sexy library [plot.ly](https://plot.ly/) which makes visualizations easier for data scientists.
* [This](http://blog.kaggle.com/2016/11/30/seventeen-ways-to-map-data-in-kaggle-kernels/) blog post on Kaggle helped me with the plots and should serve the same purpose to you.

Appropriate credits should be given to my teammates: [Chris](https://github.com/cdglasz) and [Vincent](https://github.com/DjAntaki)

Let's get started!

## The Data
First, let's see what the data looks like by using Pandas. You can download part of the data [here](https://github.com/Pulkit-Khandelwal/blogs-notebooks/tree/master/Basemap). The file is named ```"migration_simplified.csv"```. This is a much condensed version of the original data but serves the purpose for this tutorial. You can see the timestamp, the latitude and longitudinal data during the migration of birds.

```
#import the required libraries
%matplotlib inline

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.basemap import Basemap
from mpl_toolkits.mplot3d import Axes3D
import pylab

#get the data using pandas
df = pd.read_csv('migration_simplified.csv')

#display the header and see first few entirs in the dataset
print df.head()
```

![image](https://github.com/Pulkit-Khandelwal/pulkit-khandelwal.github.io/blob/master/_blog/post_3_img_4.png)
