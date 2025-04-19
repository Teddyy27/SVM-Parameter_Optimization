# Optimized SVM and Random Forest Classification

## Overview
This repository contains a Python implementation of an optimization algorithm applied to the "Wine Quality" dataset from the UCI Machine Learning Repository. The task involves optimizing the Random Forest Classifier model using 100 iterations and reporting the best parameters for each sample. Additionally, the convergence graph for the sample with the maximum accuracy is plotted.

## Dataset
The dataset used in this project is the "Wine Quality" dataset, which is available from the UCI Machine Learning Repository. This dataset contains data about various chemical properties of wine, with the goal of predicting the quality of the wine based on these properties.

- **Dataset Characteristics**: Multivariate
- **Number of Instances**: 4898  
- **Number of Features**: 11  
- **Task**: Regression  

You can access and download the dataset via the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/360/air+quality).

## Objective
The objective of this project is to:
1. Split the dataset into training and testing sets using a 70-30 ratio for 10 different samples.
2. Optimize the Random Forest model parameters (`n_estimators`, `max_depth`, `min_samples_split`) using 100 iterations to achieve the best accuracy.
3. Plot the convergence graph of the best performing sample, showing the fitness (best accuracy) over the iterations.
4. Report the best parameters and accuracies for each sample and display the results.

## Approach: Random Forest Optimization
The project follows the approach outlined below for the optimization of the Random Forest model:

1. **Data Preprocessing**:  
   - The dataset is loaded using the `ucimlrepo` Python package.
   - The features and target labels are extracted from the dataset.
   - The data is split into training and testing sets, with a 70-30 ratio for each of the 10 samples.

2. **Random Forest Optimization**:  
   - For each sample, the Random Forest Classifier is optimized using random hyperparameters:
     - `n_estimators`: The number of trees in the forest.
     - `max_depth`: The maximum depth of each tree.
     - `min_samples_split`: The minimum number of samples required to split an internal node.
   - The model is trained and evaluated using accuracy as the evaluation metric.

3. **Convergence Plot**:  
   - A convergence plot is generated for the best sample, showing how the accuracy improves over the iterations.

4. **Results**:  
   - The results for each sample, including the best accuracy and corresponding hyperparameters, are stored in a CSV file (`optimization_results.csv`).
   - The best performing sample's convergence graph is plotted to visualize the model's improvement during optimization.


### Convergence Graph for Best Accuracy
This plot represents the improvement in best accuracy over 100 iterations for the best-performing sample (among the 10 tested):


![Convergence Plot](https://github.com/user-attachments/assets/dd4803a0-da16-48fa-824c-09b36328e4c8)

**Interpretation:**
- **X-axis**: Iteration number (logged every 10 iterations)
- **Y-axis**: Best accuracy found up to that iteration
- The plot reflects how progressively better hyperparameters are found.


## Conclusion
- Even with just 50 training samples, hyperparameter tuning of the Random Forest Classifier achieved accuracies above 95%.
- Random search for tuning `n_estimators`, `max_depth`, and `min_samples_split` effectively identified optimal configurations.
- The Random Forest model showed robust performance across multiple samples.
- Random search, while simple, proved effective in optimizing the Random Forest model for high accuracy.

