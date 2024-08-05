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

![Correlation Matrix](https://github.com/nadiamahzan/python-technical-assessment/blob/main/correlation_matrix.png)

## Training Model

1. Please run the [data modelling](https://github.com/nadiamahzan/python-technical-assessment/blob/main/04_classification.ipynb) to train the model to predict which machine learning model performs the best on the dataset. 

