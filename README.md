# Leveraging Automated Deep Learning (AutoDL) in Geoscience

A new paradigm that generates high-quality pipeline of Machine Learning (ML) or Deep Learning (DL) with less to no human assistance is called AutoML or AutoDL. AutoDL has been implemented in many domains such as computer science, healthcare, natural labguage processing, and many more. However, the implementation of it within the Geoscience domain is not yet seen.

The codes within this repository explored the possibility of AutoDL implementation for several geoscientific tasks such as: (1) Lithology prediction, (2) S-wave velocity ($V_s$) prediction, and (3) Total Organic Carbon or TOC prediction.

This repository is intended for one of the requirement of Computer and Geoscience Journal, elsevier.

## Table of Contents
There are four folders which are presented within the repository:
1) **Lithology Prediction** (classification task): For the three North Sea wells, acting as the blind well. For each of the wells, 3 conventional ML algorithms (Support Vector Classifier, SVC; Random Forest, RF; and Extreme Gradient Boosting; XGB) are compared with several AutoDL algorithms (Artifical Neural Network/Feed-Forward, FF; and Convolutional Neural Network; CNN). Varying scaling mechanisms and numbers of trials-epochs are tested
2) **$V_s$ prediction** (regression task): Similar settings and comparisons as Lithology Prediction task
3) **TOC Prediction - Scenarion 1** (regression task): For the three wells from Horn River Basin. Similar comparison with the previous tasks. However, Scenario 1 means that the prediction is only performed for several points which are the actual TOC is known (not the whole points within the well)
4) **TOC Prediction - Scenarion 2** (regression task): Similar settings and comparisons as the previous task. However, Scenario 2 means that the prediction is performed on the whole points within the well. After 3 best known algorithms is choosen for the task, then the interpolation of TOC is performed, where the algorithm which generate the least RMSE and has the closest TOC values to the reference is chosen.

## Installation

This project requires Python 3.8 or higher and the following packages:
