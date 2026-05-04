# Diabetes-Prediction
Comparing Machine Learning Models for Diabetes Prediction Using NHANES Data

1. Introduction
Diabetes is a chronic condition characterized by elevated blood glucose levels due to insufficient insulin production or ineffective insulin utilization. Globally, it affects 8.5% of adults, with 34.2 million cases in the U.S., and causes 1.6 million deaths annually (WHO). Normal glucose levels range from 70 to 99 mg/dL; a level of ≥126 mg/dL indicates diabetes [1]. Risk factors include age, genetics, diet, and hypertension. Unmanaged diabetes leads to complications such as cardiovascular disease and kidney failure.
Currently, there is no permanent cure [2]; however, early detection and management through lifestyle changes, such as diet and exercise, can help prevent Type 2 diabetes. Programs like the CDC's National Diabetes Prevention Program can also assist in these lifestyle changes [3].
Healthcare produces large datasets from EHRs, lab results, and hospital records. Manual diagnosis is susceptible to errors and can miss hidden patterns, making automated prediction essential. Techniques like data mining, preprocessing, feature selection, and machine learning algorithms are increasingly utilized in healthcare to enhance early diagnosis and automate diabetes prediction by uncovering hidden patterns in medical data.

3. Problem Statement
Selecting the right features and classifiers is one of the most important challenges in developing accurate machine learning models for disease prediction. In this work, we used Pearson’s correlation method to identify relevant features. Diabetes, a major public health concern, often remains undiagnosed or is detected late, leading to severe health complications. Traditional predictive approaches mainly rely on laboratory biomarkers, disregarding socioeconomic, lifestyle, and dietary factors that may significantly influence risk. This study addresses this gap by leveraging the NHANES 2017–2018 dataset to build and compare four machine learning models: Logistic Regression, Support Vector Machine, Random Forest, and Decision Tree. To identify relevant features, we performed a Pearson’s correlation analysis.
The goal is to find a model that accurately predicts diabetes status while balancing performance metrics such as accuracy, ROC-AUC, precision, and recall. By integrating diverse data sources and evaluating models beyond accuracy, this research aims to improve early detection and support equitable public health interventions.

5. Methods
3.1. Dataset and feature selection
3.1.1. Dataset
For this study, we utilized publicly available data from the 2017-2018 National Health and Nutrition Examination Survey (NHANES)—an annual U.S. survey involving approximately 5,000 individuals who participate in interviews and undergo health examinations—to inform our analysis [4].
This survey, conducted by the Centers for Disease Control and Prevention (CDC), is unique in that it provides nationally representative data to assess the health and nutritional status of adults and children in the United States, integrating interviews, physical exams, and laboratory tests.
3.1.2. Data Attributes
This project will utilize data from the 2017-2018 survey cycles, which include approximately 10,000 participants. From its various datasets, the following variables were selected for this study. DIQ010 is the outcome variable used to determine whether the patient has diabetes.
3.2. Data preprocessing
Preprocessing helps transform data to enable the creation of a better machine learning model, resulting in higher accuracy. Preprocessing performs various functions, including merging datasets by their key components (SEQN), removing or imputing missing values, data normalization, and feature selection to enhance data quality.
The five different datasets were merged into a single comprehensive master dataset, which contains all the previously mentioned features. Categorical features were converted into numerical.
3.2.1. Missing data identification and handling
After conducting exploratory data analysis to assess data completeness, missing values were identified using summary statistics functions in Python (Table 2) and visualization tools, such as heatmaps, to identify patterns and correlations in missingness.
Rows with missing values in essential variables like INSULIN and ADO were removed to maintain data integrity. Categorical variables (e.g., education level, marital status) were imputed using mode values. K-Nearest Neighbors (KNN) imputation was considered for the remaining features based on relationships among variables. After cleaning and removing data, 893 samples were classified as diabetic, and 7,985 were classified as non-diabetic.
3.2.2. Feature selection
Pearson’s correlation method identifies relevant features by calculating the correlation coefficient, which measures the relationship between inputs and outputs, with values ranging from −1 to 1. Values above 0.5 or below −0.5 indicate significant correlation, while zero indicates no correlation.
