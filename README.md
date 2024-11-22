# Medical-Representative-Sales-Analysis-Using-Machine-Learning - DEPI_Final_Project
Final project of DEPI (IBM Data Science Track)

## Predicting Doctors' Prescribing Behaviour

### Overview
Medical representatives play a vital role in the pharmaceutical industry by bridging the gap between pharmaceutical companies and healthcare professionals. This project focuses on analyzing the factors that influence doctors' prescribing behaviours and developing a supervised machine-learning model to predict the likelihood of doctors prescribing drugs from a local pharmaceutical company. Using the AdaBoost algorithm, the model achieved an accuracy of 82% and an F1-score of 87%. Key insights regarding factors such as doctor age, specialty, and location were also analyzed, providing useful guidance for optimizing sales strategies.

This project aims to leverage machine learning techniques to predict **doctors' prescribing behaviours** based on their profiles. By analyzing features such as specialty, age, location, and class, we develop a model that predicts whether a doctor will prescribe one of the drugs produced by a local pharmaceutical company.

### Problem Statement
Medical representatives face a challenge in persuading doctors to prescribe their company’s drugs when several other brands offer the same active ingredients. Understanding the factors that influence prescribing decisions will allow companies to optimize their representatives' efforts. Therefore, the primary problem this project addresses is predicting whether a doctor, based on specific features, will prescribe a drug from the local company.

### Objectives
The key objectives of this project are:
- To determine the factors influencing doctors’ prescribing behaviours.
- To analyze the relationships between different variables, including doctor age, specialty, and location.
- To build a supervised machine learning model capable of predicting whether a doctor will prescribe a local company’s generic drugs.

### Literature Review
Several studies have examined how pharmaceutical companies can improve their sales strategies by understanding prescribing patterns. Studies indicate that doctor’s specialty, experience, and location significantly impact prescribing habits. Various machine learning algorithms, including Decision Trees, Random Forest, and AdaBoost, have been applied to similar problems in healthcare. AdaBoost, known for enhancing weak learners, is one of the most efficient algorithms for classification tasks with imbalanced data.

## 3. Methodology 

### 3.1 Data Collection
The dataset for this project was sourced from two tables: `medicine_table` and `doctor_table`. These tables contained details about doctors, their specialties, locations, and prescribing behaviours.

### 3.2 Data Preprocessing
Data preprocessing involved the following steps:
- **Handling Missing Values:** Missing data were imputed using mean or dropped techniques.
- **Feature Encoding:** Categorical features such as specialty and location were encoded using one-hot and label encoding.
- **Normalization:** Continuous variables like age and years of experience were normalized using MinMaxScaler to bring all variables into comparable ranges.
- **Skewness:** Checked skewness of every column, which was acceptable, so no change was required.

## 4. Exploratory Data Analysis (EDA)

#### 4.1 Correlation Heatmap
A correlation plot was generated to identify relationships between the features. Key findings include:
- Doctor’s Class and Examination Price were highly correlated with prescribing behaviour.
- Drug Price showed a poor correlation with prescribing behaviour.

#### 4.2 Key insights from the graphs:
Bar charts were used to visualize the distribution of categorical features:
- **Specialties:** General Practitioners (GPs) and Chest specialized doctors were found to be more likely to prescribe the local company’s drugs.
- **Class Distribution:** Class B doctors were the most frequent prescribers of generic drugs.
- **Drug Price:** Prices like (50, 100, 120, 150) were found to be more likely to lead to prescriptions, unlike prices higher than or equal to 250.
- **Place of Work:** Clinic doctors were found to be more likely to prescribe the local company’s drugs, while Hospital doctors tended to be neutral.
- **Doctors with class 'B'** are the most likely to prescribe the company's medicines for their patients.
- **Doctors who work at hospitals** are slightly more numerous than those working in clinics when it comes to prescribing the company's medicines.
- **Doctors whose examination price** is '30' or '50' are the most likely to prescribe the company's medicines, followed by those charging '75'.
- the prices of medicine are fairly consistent, with a median around 35 and a range from 20 to 45, without any extreme outliers.
- The width of the boxplot indicates the variability in examination prices, with a median around 100 and a range from 50 to 200, suggesting a consistent pricing structure for examinations within this dataset.

### 4.2 Feature Importance
The most important features of the AdaBoost model were:
- **Doctor’s Class:** The most influential factor in predicting prescription behaviour.
- **Doctor’s Examination Price:** Doctors with relatively low examination prices were more likely to prescribe local company products.

## 5. Model Development

### 5.1 Model Selection
We tested several machine learning models, including Decision Trees, Random Forests, Gradient Boost, and Support Vector Machines. After extensive experimentation, the AdaBoost algorithm was selected due to its superior performance.

### 5.2 Model Training
The dataset was split into an 80:20 ratio for training and testing. The AdaBoost model was trained on the training set, with hyperparameters optimized through grid search. We evaluated the model using metrics such as accuracy and F1-score.

### 5.3 Model Performance
The final AdaBoost model achieved:
- **Accuracy:** 84.6%
- **F1-Score:** 88.2%

## 6. Conclusion
This project successfully applied supervised machine learning to predict doctors' prescribing behaviours. By analyzing features such as class, specialty, and examination price, the AdaBoost model achieved an accuracy of 84.6% and an F1-score of 88.2%. These results can help pharmaceutical companies optimize their marketing strategies, save resources, and better target healthcare professionals.

