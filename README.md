Q1. What is anomaly detection and what is its purpose?
Anomaly detection: Also known as outlier detection, it is the process of identifying rare items, events, or observations that raise suspicions by differing significantly from the majority of the data.

Purpose: Anomaly detection aims to:

Identify unusual patterns that do not conform to expected behavior.
Flag potential outliers that may indicate errors, fraud, or interesting events in data.
Q2. What are the key challenges in anomaly detection?
Challenges:
Unlabeled Data: Often, anomaly detection is performed without labeled data, making it challenging to define what constitutes normal versus anomalous.
Scalability: Efficiently handling large volumes of data while maintaining detection accuracy.
Imbalanced Data: Anomalies are typically rare compared to normal instances, leading to imbalanced datasets.
Complexity: Differentiating between anomalies and legitimate variations in data can be intricate.
Real-Time Detection: Needing to detect anomalies promptly in streaming data or time-series data.
Q3. How does unsupervised anomaly detection differ from supervised anomaly detection?
Unsupervised Anomaly Detection:

Detects anomalies in unlabeled data where anomalies are identified based on deviations from normal data points.
Does not require prior knowledge or labeled examples of anomalies.
Examples: Distance-based methods (e.g., KNN), density-based methods (e.g., LOF), and clustering-based methods.
Supervised Anomaly Detection:

Requires labeled data where anomalies are explicitly identified and labeled.
Models are trained to distinguish between normal and anomalous instances based on labeled examples.
Examples: Classification algorithms (e.g., SVM, Random Forest) trained on labeled anomaly data.
Q4. What are the main categories of anomaly detection algorithms?
Main Categories:
Statistical Methods: Based on statistical models and distributions (e.g., Gaussian distribution).
Machine Learning Methods:
Supervised Learning: Classifiers trained on labeled data.
Unsupervised Learning: Detect anomalies based on deviations from normal data.
Proximity-Based Methods: Measure distances or densities to determine anomalies (e.g., KNN, LOF).
Clustering-Based Methods: Detect anomalies as points in low-density regions or clusters.
Model-Based Methods: Build probabilistic models of normal data and identify deviations.
Q5. What are the main assumptions made by distance-based anomaly detection methods?
Assumptions:
Anomalies are instances that are far from most other instances in the feature space.
Normal instances are clustered together or have similar densities.
Distance metrics accurately reflect the similarity or dissimilarity between data points.
Q6. How does the LOF algorithm compute anomaly scores?
LOF (Local Outlier Factor) Algorithm: Measures the local deviation of density of a data point with respect to its neighbors.

Steps to compute LOF:
Calculate Reachability Distance: Measure how close each point 
𝑝
p is to its 
𝑘
k-th nearest neighbor 
𝑁
𝑘
(
𝑝
)
N 
k
​
 (p).
Calculate Local Reachability Density (LRD): Average reachability distance of 
𝑝
p to its neighbors.
Calculate Local Outlier Factor (LOF): Ratio of the LRD of 
𝑝
p to the LRD of its neighbors, indicating how much more or less dense 
𝑝
p is compared to its neighbors.
Q7. What are the key parameters of the Isolation Forest algorithm?
Isolation Forest Parameters:
n_estimators: Number of trees in the forest (higher values reduce variance).
max_samples: Number of samples to draw from the dataset to train each tree (lower values increase the model's susceptibility to anomalies).
contamination: Expected proportion of anomalies in the data (affects the decision threshold for anomaly scores).
Q8. If a data point has only 2 neighbors of the same class within a radius of 0.5, what is its anomaly score using KNN with K=10?
KNN Anomaly Score Calculation:
Anomaly score is inversely proportional to the density of neighbors within a specified radius or 
𝑘
k nearest neighbors.
Given only 2 neighbors of the same class within a radius of 0.5:
The anomaly score would be high because the point is in a sparse neighborhood relative to 
𝑘
=
10
k=10.
Q9. Using the Isolation Forest algorithm with 100 trees and a dataset of 3000 data points, what is the anomaly score for a data point that has an average path length of 5.0 compared to the average path length of the trees?
Isolation Forest Anomaly Score Calculation:
Anomaly score is based on the average path length (number of splits) a point takes to reach an external node across all trees.
If a point has an average path length of 5.0:
Compare it to the average path length of points in the dataset.
Anomaly score is typically higher for points with shorter average path lengths (indicating they are easier to isolate).
