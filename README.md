# Breast_Cancer_data_prediction_KNN
**In this repository, the dataset is trained using the K-Nearest Neighbors (KNN) algorithm with various distance metrics. Key insights, results, and visualizations are provided below.**  

📊 Dataset Summary  
📚 Name of Dataset : Diagnostic Wisconsin Breast Cancer Database  
📚 Source: https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic  
🧾 Size: 569 samples  
🔧 Features: 30  
  
🔍 Distance Metrics Tested & Their Accuracy:  
Minkowski (p=3): 0.97  
Cosine: 0.96  
Euclidean: 0.96  
Manhattan: 0.96  
Chebyshev: 0.95  
Mahalanobis: 0.80  
Hamming: 0.63  

📊 What these numbers tell us:  
  
1) The Minkowski distance with p=3 performed best, slightly edging out Euclidean and Manhattan distances. This makes sense since Minkowski generalizes those metrics and can better adapt to the dataset's geometry. 

2) Cosine distance’s strong performance (~96%) highlights its effectiveness in measuring similarity by angle rather than magnitude — ideal when feature patterns matter more than scale.  

3) Mahalanobis distance’s comparatively low accuracy (79%) might be due to estimation challenges of the covariance matrix or the assumption of feature distributions.  

4) Hamming distance lagged significantly at 63%, reflecting its unsuitability for continuous numerical features without preprocessing like discretization.  

📉 Visual Analysis  
1) Comparing Confusion Matrices for KNN with Different Distance Metrics  
   ![Confusion_matrix](https://github.com/user-attachments/assets/4a9b44cc-2ca2-4f40-bca8-27bc65543b88)  

2) Bar chart of accuracy scores.  
   ![Accuracy Bar Graph](https://github.com/user-attachments/assets/72a64709-cddf-49db-8dcf-b97ed10864c1)   


❓ Why did Hamming perform poorly?  
Hamming distance is designed to count mismatches between discrete or binary features. Although the target labels are binary, the input features in this dataset are continuous numeric values. When Hamming compares continuous features, almost every feature differs, making distances less informative and leading to poor neighbor selection and lower accuracy.  

💡 Conclusions:  
1) Choosing an appropriate distance metric aligned with data characteristics is critical for maximizing KNN performance.  
2) For continuous features, Minkowski, Euclidean, Manhattan, and Cosine distances are generally more effective.  
3) Advanced metrics like Mahalanobis require careful consideration of dataset-specific properties.  
4) Discrete metrics such as Hamming demand proper feature transformation to be applicable.  
