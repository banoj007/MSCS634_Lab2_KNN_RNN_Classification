# Name: Banoj Kumar Jena  
# Course: MSCS 634 - Machine Learning  
# Lab Title: Lab 2 - Classification Using KNN and RNN Algorithms

Objective  
The purpose of this lab is to compare the performance of two distance-based classification models: K-Nearest Neighbors (KNN) and Radius Neighbors Classifier (RNN) using the Wine dataset from the sklearn library. The lab involves testing different values of the hyperparameters k for KNN and radius for RNN and analyzing how they affect classification accuracy. The goal is to gain a better understanding of how hyperparameter tuning influences model performance.

Dataset Description  
- Dataset: Wine Dataset from sklearn  
- Features: 13 numerical chemical properties of wine  
- Target: 3 wine categories (class_0, class_1, class_2)  
- Class distribution:  
  - class_0: 59 samples  
  - class_1: 71 samples  
  - class_2: 48 samples

Methodology  

Step 1: Load and Preprocess the Dataset  
- The dataset was split into 80% training and 20% testing sets using train_test_split.  
- Features were standardized using StandardScaler to ensure fair distance calculations for both KNN and RNN classifiers.

Step 2: Implement K-Nearest Neighbors (KNN)  
- KNN classifier was tested with various values of k: 1, 5, 11, 15, and 21.  
- Accuracy was calculated for each value using the test dataset.  
- The highest accuracy achieved was 100% for k=11, k=15, and k=21.

Step 3: Implement Radius Neighbors (RNN)  
- RNN classifier was tested with radius values: 350, 400, 450, 500, 550, and 600.  
- Due to the high radius values (relative to the standardized data), many test samples were classified as outliers.  
- The accuracy remained constant at 38.89% across all radius values.

Step 4: Visualization and Comparison  
- Accuracy vs. k-value was plotted for KNN.  
- Accuracy vs. radius was plotted for RNN.  
- KNN showed consistent and improving performance with higher k values, while RNN accuracy was significantly lower and unaffected by radius changes.

Results Summary  

KNN Classifier:  
- k = 1 → Accuracy: 97.22%  
- k = 5 → Accuracy: 97.22%  
- k = 11 → Accuracy: 100%  
- k = 15 → Accuracy: 100%  
- k = 21 → Accuracy: 100%

RNN Classifier:  
- Radius = 350 → Accuracy: 38.89%  
- Radius = 400 → Accuracy: 38.89%  
- Radius = 450 → Accuracy: 38.89%  
- Radius = 500 → Accuracy: 38.89%  
- Radius = 550 → Accuracy: 38.89%  
- Radius = 600 → Accuracy: 38.89%

Observations  
- KNN significantly outperforms RNN in this lab.  
- KNN provides stable and excellent classification results when k is set to 11 or higher.  
- RNN accuracy remained poor due to outlier predictions caused by inappropriate radius values for standardized data.  
- Feature scaling is essential, but even after scaling, the chosen radius values were ineffective.

Challenges Faced  
- Choosing appropriate radius values for the RNN classifier was challenging.  
- A majority of RNN predictions returned outlier labels (-1), which reduced the overall accuracy.  
- Tuning the radius parameter required more domain insight or automated techniques like grid search.

Conclusion  
This lab demonstrated that the K-Nearest Neighbors classifier is much more effective than Radius Neighbors for the Wine dataset under the tested conditions. KNN performed with near-perfect accuracy at higher k values, while RNN struggled to make valid predictions due to inappropriate radius selection. Based on this study, KNN is recommended for datasets with well-separated classes and standardized features. RNN may require more careful parameter tuning and a better understanding of data distribution.

Files Included in the Repository  
1. Lab2_KNN_RNN_Wine.ipynb – The complete Jupyter Notebook with all steps and results.  
2. README.md – This documentation file containing the summary, results, and insights from the lab.
