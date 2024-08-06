# python-technical-assessment
Python technical assessment for Etiqa

## Installation
1. Clone the repository:
```bash
git clone https://github.com/nadiamahzan/python-technical-assessment.git
```

2. Create virtual environment, use python 3.7 and above
```bash
py -3.10 -m venv venv
```

3. Install requirements.txt
```bash
py -3.10 -m venv venv
```

## Data Preparation 

Include doing data formatting, handle missing value, data preprocessing, feature engineering and EDA.

1. Start with [data formatting](https://github.com/nadiamahzan/python-technical-assessment/blob/main/01_data_formatting.ipynb) by running all the codes inside it. In here, we would check the format of each column and reformat the values in the column if there's any value that are not in uniform with the others.

2. Next, run the [missing value](https://github.com/nadiamahzan/python-technical-assessment/blob/main/02_replace_missing_value.ipynb) file. In this file, we would remove the rows in columns with less than 10% missing values. For rows with more than 80% of missing value, we would understand the purpose of the column before dropping it out. 

In the case that the column with a lot of missing values in it but is not being dropped (in this project, it's the column **months_since_last_deliquency**), we would create another category called 'Not Available' to assign to the missing value. This is to avoid missing any important data. Using mean, mode or median imputing is not suitable for this column as the column 'months_since_last_deliquency' refers to a situation where a borrower is late or overdue on a payment.

3. Afterwards, run the file [eda and feature engineering](https://github.com/nadiamahzan/python-technical-assessment/blob/main/03_eda_%26_feature_engineering.ipynb). Columns with datetime datatype are converted to days and years and afterwards are put into categories to be processed. Label encoding and ordinal encoding are then used to encode categorical data tp change it into numerical data to be processed. Afterwards, we do a correlation coefficient to see the correlation between the columns. 

![Correlation Matrix](https://github.com/nadiamahzan/python-technical-assessment/blob/main/eda_results/correlation_matrix.png)

From the figure above, we can see that there are not many columns that has a strong correlation with our target variable 'repay_fail'. 

Afterwards, we use techniques such as Cramer's V, Univariate Selection and Feature Importance to pick only the top 10 of the columns to be used for data modelling. 

Cramer's V result:

![Cramer's V ](https://github.com/nadiamahzan/python-technical-assessment/blob/main/eda_results/cramer's_v.PNG)

Univariate Selection result:

![Univariate Selection](https://github.com/nadiamahzan/python-technical-assessment/blob/main/eda_results/univariate_selection.PNG)

Feature Importance result:

![Feature Importance](https://github.com/nadiamahzan/python-technical-assessment/blob/main/eda_results/feature_importance.png)

The results for the top 10 features are similar to each other. Cramer's V is a test to see the correlation between two categorical features hence we cannot use the results. We would use the features in Univariate Selection as it has higher and consistent scores throughout the columns compared to Feature Importance.

## Training Model

Please run the [data modelling](https://github.com/nadiamahzan/python-technical-assessment/blob/main/04_classification.ipynb) to train the model to predict which machine learning model performs the best on the dataset. 

In here, we use multiple classification model to train our data on. The models used are **Logistic Regression**, **Artificial Neural Network**, **Support Vector Machine**, **Naive Bayes** and **K-Nearest Neighbours**. These 4 models  The key metrics used to test these machine learning models are accuracy, precision, recall and F1 score. We also run a confusion matrix to see how many of the tests data are true positive and true negative.

### Logistic Regression Results:

![lr_results](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/lr_results.PNG)

Confusion Matrix:

True Positives = 1259
True Negatives = 8022
False Positives = 12
False Negatives = 47

![lr_cm](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/lr_cm.png)

### Artificial Neural Network:

![ann_results](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/ann_results.PNG)

Confusion Matrix:

True Positives = 1129
True Negatives = 8033
False Positives = 1
False Negatives = 177

![ann_cm](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/ann_cm.png)

### Support Vector Machine:

![svm_results](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/svm_results.PNG)

Confusion Matrix:

True Positives = 1264
True Negatives = 8026
False Positives = 8
False Negatives = 42

![svm_cm](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/svm_cm.png)

### Naive Bayes:

![nb_results](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/nb_results.PNG)

Confusion Matrix:

True Positives = 1243
True Negatives = 7995
False Positives = 39
False Negatives = 63

![nb_cm](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/nb_cm.png)

### K-Nearest Neighbours:

![knn_results](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/knn_results.PNG)

Confusion Matrix:

True Positives = 903
True Negatives = 8009
False Positives = 25
False Negatives = 403

![knn_cm](https://github.com/nadiamahzan/python-technical-assessment/blob/main/classification_results/knn_cm.png)


### Conclusion:

From the results of the above models, SVM model performs the best with the highest score for accuracy, recall and its F1 score. In terms of precision, ANN model has a slightly higher results than SVM, but overall SVM still performs the best. 

In the terms of finding the true positives and true negatives, SVM also scored the highest in these part. 