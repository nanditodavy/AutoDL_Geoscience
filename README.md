# Leveraging Automated Deep Learning (AutoDL) in Geoscience

AutoML or AutoDL is a new paradigm that generates high-quality pipelines of Machine Learning (ML) or Deep Learning (DL) with little to no human assistance. AutoDL has been implemented in many domains such as computer science, healthcare, natural language processing, and many more. However, its implementation within the Geoscience domain has not been seen yet.

In this study, an available open-source package called Auto-Keras is utilized, which provides further details and installation procedures in the following link: [Auto-Keras](https://autokeras.com/).


The codes within this repository explored the possibility of AutoDL (Auto-Keras) implementation for several geoscientific tasks such as: (1) Lithology prediction, (2) S-wave velocity ($V_s$) prediction, and (3) Total Organic Carbon or TOC prediction.

This repository is intended for one of the requirement of Computer and Geoscience Journal, elsevier.

Note that the dataset for the North Sea Wells (dataset A) are compiled from [this Github repo](https://github.com/bolgebrygg/MalenoV), while the Horn River Basin dataset (dataset B) is **confidential**. Therefore, the dataset will not be available in this repository.

The dataset is withheld to protect the originality of the code

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

## Instructions
for **Lithology Prediction**:
1. For well XX (Well 15, 25, or 32), run all the `wellXX_AutoDL__.ipynb` and `wellXX_Conv_ML.ipynb` notebooks. The point-per-point accuracy for each algorithm is obtained in these notebooks (**Table 4** in the manuscript)
2. Several .*csv files of the predicted lithology classes will be generated, such as `wellXX_CONV_facies.csv`, `wellXX_FF1_facies.csv`, `wellXX_FF2_facies.csv`, `wellXX_FF3_facies.csv`, `wellXX_FF4_facies.csv`, `wellXX_CNN1_facies.csv`, and `wellXX_CNN1_facies.csv`
3. Run the `combine_result_wellXX.csv` to compile the results into one figure. For the three wells, then these figures are combined vertically using third-party website such as [this website](https://pinetools.com/merge-images) in order to generate **Figure 3** in the manuscript.

for **$V_s$ Prediction**:
1. For well XX (Well 15, 25, or 32), run all the `wellXX_AutoDL_ALGO_Vs.ipynb` and `wellXX_Conv_ML_Vs.ipynb` notebooks. The RMSE and $R$ values for each algorithm is obtained in these notebooks (**Table 5** in the manuscript)
2. Several .*csv files of the predicted $V_s$ will be generated, such as `well_XX_Vs_pred_SVM.csv`, `well_XX_Vs_pred_RF.csv`, `well_XX_Vs_pred_XGB.csv`, `well_XX_Vs_pred_FF1.csv`, `well_XX_Vs_pred_FF2_T100_E3.csv`, `well_XX_Vs_pred_FF3.csv`, `well_XX_Vs_pred_FF4_T100_E3.csv`, `well_XX_Vs_pred_CNN1_T100_E1.csv`, and `well_XX_Vs_pred_CNN2_T100_E1.csv`
3. Run the `combine_result_wellXX_Vs.csv` to compile the results into one figure. For the three wells, then these figures are combined vertically using third-party website such as [this website](https://pinetools.com/merge-images) in order to generate **Figure 4** in the manuscript.

for **TOC Prediction (Scenario 1)**
1. For well XX (Well Maxhamish, McAdam, or Komie), run all the `TOC_S1_AutoDL_XX_ALGO.ipynb` and `TOC_S1_ML_XX_CONV.ipynb` notebooks. 
2. Several .*csv files of the predicted TOC (only for the points where actual TOC is known) will be generated, such as `TOC_Pred_XX_CONV.csv`, `TOC_Pred_XX_FF1_FF2.csv`, `TOC_Pred_XX_FF3_FF4.csv`, `TOC_Pred_XX_CNN1.csv`, `TOC_Pred_XX_CNN2.csv`, `TOC_Pred_XX_CNN3.csv`, and `TOC_Pred_XX_CNN4.csv`.
3. Run the `combine_result_XX_TOC_S1.csv` to compile the results into one figure. For the three wells, then these figures are combined vertically using third-party website such as [this website](https://pinetools.com/merge-images) in order to generate **Figure 5** in the manuscript. The RMSE and $R$ values for each algorithm is obtained in these notebooks (**Table 6** in the manuscript)

## Contact
Discussions or questions can be addressed to Nandito Davy's email at nanditodavy96@gmail.com or his office at The Department of Geoscience, College of Petroleum and Geosciences, KFUPM, Dhahran, Kingdom of Saudi Arabia
