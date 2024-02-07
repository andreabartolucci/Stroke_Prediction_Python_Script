# Stroke Prediction Python Script

# Stroke Prediction Python Script

This GitHub repository contains a Python script designed to address a binary categorical classification problem with the target variable being stroke prediction. The script performs various tasks to preprocess the data and build predictive models. With a focus on maximizing recall to minimize false negatives, the script follows a comprehensive workflow:

1. Exploratory Data Analysis (EDA):
   - Outlier removal using the Interquartile Range (IQR) method.
   - Handling missing values by replacing them with the medians.
   - Applying one-hot-encoding for categorical nominal variables.
   - Utilizing ordinal encoding for categorical ordinal variables.
   - Performing Box-Cox transformation for continuous variables.
   - Creating interactions of continuous variables with male, hypertension, and heart disease indicators.
   - Including polynomial transformation (power of 2) for continuous variables.
   - Adding a constant term for modeling.

2. Pre-processing:
   - Balancing the dataset by resampling the positive stroke cases to achieve a balanced distribution (around 50% stroke=0 and 50% stroke=1). The original dataset had a frequency of positive strokes equal to 4.8%.

3. Modeling:
   - Fitting three models: logistic regression (linear model), decision tree (non-linear model), and random forest (ensemble model).
   - Evaluating the learning curves, determining that PCA and standard scaler were unnecessary for all models, leading to their exclusion from the pipelines.

4. Model Selection and Validation:
   - Determining the best train/test split ratio based on the learning curve.
   - Performing 5-fold cross-validation for model estimation.
   - Utilizing grid search to find the best combination of parameters for each model.

5. Model Testing:
   - Selecting models based on recall as the relevant metric.
   - Prioritizing the minimization of false negatives (FN) to avoid misclassifying patients at risk of stroke.
   - Evaluating recall as TP/(TP+FN), maximizing it to minimize the number of false negatives.

6. Performance Metrics:
   - Plotting the confusion matrix to visualize false positives, false negatives, true positives, and true negatives.
   - Printing recall, precision, and F1 score for each model.
   - Comparing these metrics, it is observed that non-linear models (decision tree and random forests) outperform the linear model (logistic regression) in this classification problem.
   - Random forest achieves the highest recall (100%) and improves precision (from 92.9% for decision tree to 96.9%), making it the superior model for stroke prediction in this dataset.

Explore this GitHub repository to access the Python script and benefit from its comprehensive workflow for stroke prediction. Gain insights into preprocessing techniques, model selection, and performance evaluation to enhance the accuracy of stroke predictions in healthcare contexts.
