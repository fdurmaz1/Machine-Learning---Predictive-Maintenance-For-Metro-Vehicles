# Machine Learning Project-Predictive Maintenance For Metro Vehicles
# NOTE: Since Github doesn't allow me to upload files with bigger that 25mb, you can download the whole project from below link;
[CLICK TO DOWNLOAD PROJECT](https://drive.google.com/drive/folders/1x8MH9qx2SO_uIojn8_Q9YZwYgkDsBBNL?usp=sharing)
## Introduction
This project focuses mainly on the critical parts of public transport, especially Metro vehicles, and aims to points the challenges of detecting faults during regular operation. Prompt and efficient fault detection can prevent interruptions and minimize damage. Currently, faults in the Air Production Unit (APU), a critical component in Metro vehicles, often go undetected based on predefined thresholds, leading to unexpected maintenance and service disruptions.
<br>
## Data preparation and feature engineering 
For the project, exploration and analysis of the variables were collected from the Air Production Unit (APU). The analogical sensors, dispersion and shape of variable distribution were studied using the Correlation relations, skewness, and histograms. 
For the categorical variables, the frequency of each variable activation was analyzed. The goal was to identify their behavior. Some inconsistencies were noted between COMP and MPG sensor values in APU, which could be due to sensor malfunctions.
The correlation between variables is also a good measure to understand how the APU system works. The heat maps that represent the correlations between variables on APU.
Based on the Correlation Heatmap analysis:
•	The attributes COMP, MPG, DV Electric, TP2, and H1 exhibit strong correlations with each other.
•	The Oil Temperature sensor shows a notable correlation with the TP3 sensor.
•	Variables Towers, Oil Level, and Caudal Impulses do not demonstrate strong correlations with other sensors.
•	The LPS sensor demonstrates its highest correlation with the TP3 sensor.
<br>
![image](https://github.com/fdurmaz1/SQL_Company_project/assets/133916817/e1df4712-9c94-4df0-b6fc-09bb0f72c611)
<br>
## Cluster Analysis
Cluster analysis is a key aspect of this project, specifically applied to the unsupervised learning section. This technique aims to group a set of objects in such a way that objects in the same group (called a cluster) are more similar to each other than to those in other groups (clusters). It's a main task of exploratory data mining, and a common technique for statistical data analysis used in many fields.
In this project, the K-means clustering algorithm is employed. K-means is a centroid-based or partitioning method. It partitions the input data into K clusters where each observation belongs to the cluster with the nearest mean. Two methods are used to determine the optimal number of clusters for the K-means algorithm:
<br>
**Elbow Method:** This method plots the variance as a function of the number of clusters. The optimal number of clusters is the point where adding another cluster doesn't improve the total variance significantly. This point resembles an "elbow" in the plot, which is how the method got its name.
<br>
![image](https://github.com/fdurmaz1/SQL_Company_project/assets/133916817/0346e7ea-1eb4-438d-b9be-e4cf89ee88b4)
<br>
**Silhouette Analysis:** This method provides a graphical representation of how well each object lies within its cluster. It gives a measure of how similar an object is to its own cluster (cohesion) compared to other clusters (separation). The silhouette ranges from -1 to +1, where a high value indicates that the object is well matched to its own cluster and poorly matched to neighboring clusters.
After determining the optimal number of clusters, K-means is applied to the standardized data, and the clustering results are visualized using Principal Component Analysis (PCA). PCA reduces the dimensionality of the data while preserving as much variance as possible, which makes it possible to visualize the high-dimensional data in a 2D plot.
<br>
![image](https://github.com/fdurmaz1/SQL_Company_project/assets/133916817/1e29938a-9ff2-457d-8086-44f2a934672c)
<br>
![image](https://github.com/fdurmaz1/SQL_Company_project/assets/133916817/1d6fc891-c99e-4c46-86d6-de4646d66173)
<br>
## Sample Prediction & Results Interpretation and Implication
In the evaluation phase of the project, the focus was on predicting the activation of the LPS sensor, an indication of pressure falling below 7 bar on the compressor, which could potentially cause the train to stop. The analysis compared the performance of Autoencoders and LSTM Autoencoders, both of which are Deep Learning (DL) techniques. DL was preferred over Machine Learning (ML) due to the high imbalance in the data set and the possibility of DL handling this imbalance more effectively than ML.

The experimental setup involved several steps, including shifting the LPS variable, removing temporal and categorical features, splitting the data into train, validation, and test sets, normalizing the data, and training the model. The performance metrics used to evaluate the models were Accuracy, Precision, Recall  was chosen as the primary evaluation metric due to its ability to measure the quality of the model's predictions irrespective of the threshold.<br>
![image](https://github.com/fdurmaz1/SQL_Company_project/assets/133916817/ee5afaf6-b434-428b-bcbd-f70f9bef2aef)
<br>
## Conclusion
In conclusion, the primary objective of our project was to predict the failure of Auxiliary Power Units (APUs) installed on trains, using their sensor data. Through our comprehensive study, we widely used clustering techniques to identify standard and outlier operation modes of the APU, and the deployment of Autoencoders for failure prediction. Our results demonstrated the efficiency of our methodologies. In particular, the peak frequency analysis allowed us to devise a notification system based on six rules, capable of predicting all the failures that occurred on APU. The clustering techniques revealed operational modes for the APUs, and our deep learning models, specifically Autoencoders, demonstrated promising results, predicting APU failures. These findings underscore the potential of our approach to enhance the predictability of APU failures, providing a foundation for future advancements in this field.


