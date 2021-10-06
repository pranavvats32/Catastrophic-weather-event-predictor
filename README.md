# Catastrophic weather events prediction
 Pranav Vats - RA1811003010225
 Vanshika Mishra - RA1811031010036

## Problem Statement
Over the years, due to extreme weather we have had many catastrophic events which have caused loss of human life and property. The current methods are complex and lack accuracy and hence not dependable.


## Objective
With the dataset that is available from the past, which provides us the information about the weather conditions over the past few years, we can implement ML algorithms such as DBSCAN and k-means clustering to predict the estimate of upcoming catastrophic weather events, which can be used to save valuable human life and property.

## Dataset Used

The weather information has been taken from the website NCEP/NCAR. The region taken for weather prediction is from latitude of 8°N to 18°N to a longitude of 72°E to 78° E which is the land area that covers Kerala, Karnataka, Goa and southern parts of Maharashtra along with arabian sea. The atmospheric variables like air temperature, vertical velocity (omega), relative humidity, specific humidity, u-wind and v-wind are taken from 1 January 1948 to 31 December 2017 are downloaded in the format of NetCDF. On daily basis, the data for all the parameters have been taken.

## Pipeline of the project

 1. Data Acquisition
 2. Data Processing
 3. Data Modeling
 4. Execution
 5. Deployment

> Each of these steps involve subsets that will be used on the dataset chosen.


## Architecture / Model 
mermaid
graph LR
A[Weather Dataset] --> B[z-score normalization]
B --> C[AFM Technique]
C --> D[DBSCAN clustering]
C --> E[k-means clustering]
D-->F[Performance analysis]
E-->F
F-->g[Compaing results] 

> The Data from the dataset is preprocessed. Data retrieval and data normalisation are part of this preparation.The extracted data is in 4D form in the data retrieval step, with latitude, longitude, day, and its associated value as four co-ordinates. The data is then converted to 2D data, with the day and value of each grid, as well as latitude and longitude as co-ordinates, for easier access. The converted data is organised in chronological order, with each year's set of values grouped together.


## Predicted Output
The Catastrophic weather events predictor allows users to easily develop models that make highly accurate predictions. We trained on dataset from the past and applied to new data forecasting the likelihood of the next weather related catastrophic event. 
The algorithm will generate probable values for an unknown variable for each record in the new data, allowing the model builder to identify what that value will most likely be.
It streamlines the data science process so that users get high-quality predictions in a fraction of the time it 
took using traditional methods, allowing them to more quickly implement those predictions and see the impact on their bottom line.

## References
 - "**[How to use machine learning for anomaly detection and condition monitoring](https://towardsdatascience.com/how-to-use-machine-learning-for-anomaly-detection-and-condition-monitoring-6742f82900d7)**"*-towardsdatascience blogs, author-Vegard Flovik*
 - "**[Machine learning architecture](https://www.educba.com/machine-learning-architecture/)**"*- by Priya Pedamkar*
 - "**[z-Score normalization](https://uomustansiriyah.edu.iq/media/lectures/6/6_2020_03_11!08_44_32_AM.pdf)**" from T4Tulorials
 - "**[in-depth k means clustering](https://jakevdp.github.io/PythonDataScienceHandbook/05.11-k-means.html)**"- from the  Python Data Science Handbook by Jake VanderPlas
 - "**[DBSCAN: Density-Based Clustering Essentials](https://www.datanovia.com/en/lessons/dbscan-density-based-clustering-essentials/)**" - by Alboukadel Kassambara
