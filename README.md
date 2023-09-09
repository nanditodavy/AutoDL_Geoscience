# Leveraging Automated Deep Learning (AutoDL) in Geoscience

A new paradigm that generates high-quality pipeline of Machine Learning (ML) or Deep Learning (DL) with less to no human assistance is called AutoML or AutoDL. AutoDL has been implemented in many domains such as computer science, healthcare, natural labguage processing, and many more. However, the implementation of it within the Geoscience domain is not yet seen.

In this study, an available open-source package called **Auto-Keras** is utilized, which the furture details and installation procedure for it can be seen in the following link: https://autokeras.com/

The codes within this repository explored the possibility of AutoDL (Auto-Keras) implementation for several geoscientific tasks such as: (1) Lithology prediction, (2) S-wave velocity ($V_s$) prediction, and (3) Total Organic Carbon or TOC prediction.

This repository is intended for one of the requirement of Computer and Geoscience Journal, elsevier.

Note that the dataset for the North Sea Wells (dataset A) are compiled from https://github.com/bolgebrygg/MalenoV, while the Horn River Basin dataset (dataset B) is **confidential**. Therefore, the dataset will not be available in this repository.

## Table of Contents
There are four folders which are presented within the repository:
1) **Lithology Prediction** (classification task): For the three North Sea wells, acting as the blind well. For each of the wells, 3 conventional ML algorithms (Support Vector Classifier, SVC; Random Forest, RF; and Extreme Gradient Boosting; XGB) are compared with several AutoDL algorithms (Artifical Neural Network/Feed-Forward, FF; and Convolutional Neural Network; CNN). Varying scaling mechanisms and numbers of trials-epochs are tested
2) **$V_s$ prediction** (regression task): Similar settings and comparisons as Lithology Prediction task
3) **TOC Prediction - Scenarion 1** (regression task): For the three wells from Horn River Basin. Similar comparison with the previous tasks. However, Scenario 1 means that the prediction is only performed for several points which are the actual TOC is known (not the whole points within the well)
4) **TOC Prediction - Scenarion 2** (regression task): Similar settings and comparisons as the previous task. However, Scenario 2 means that the prediction is performed on the whole points within the well. After 3 best known algorithms is choosen for the task, then the interpolation of TOC is performed, where the algorithm which generate the least RMSE and has the closest TOC values to the reference is chosen.

For the classification task, comparison is done by looking at their point-per-point accuracy value; from the 18 lithology classes, the predicted lithology should be exactly the same as the actual lithology to be considered "correct". The algorithm which generates the largest accuracy value is preferred.

On the other hand, the regressions tasks will used RMSE and $R$ value (Pearson's correlation). The best algorithm should generate the least RMSE but the highest $R$.

## Installation

This project requires Python 3.8 or higher and the following packages:

autokeras==1.0.20

keras==2.9.0

Keras-Preprocessing==1.1.2

keras-tuner==1.1.3

matplotlib==3.5.3

mkl-random==1.2.2

numpy==1.21.5

pandas==1.3.5

scikit-elm==0.21a0

scikit-learn==1.0.2

seaborn==0.12.0

tensorflow==2.9.1

xgboost==1.6.2

## Contact
Discussions or questions can be addressed to Nandito Davy's email at nanditodavy96@gmail.com or his office at The Department of Geoscience, College of Petroleum and Geosciences, KFUPM, Dhahran, Kingdom of Saudi Arabia
