# Heart-Disease-Prediction-ML-Pipeline-with-AWS-S3-Snowflake
This project develops a heart disease prediction model using AWS S3, Snowflake, and Machine Learning. Data is stored in S3, loaded into Snowflake for analysis, and processed using SQLAlchemy. kNN and SVM models are trained with GridSearch for hyperparameter tuning, and performance is evaluated in a Jupyter Notebook.


# Project Path
│── data/                          
│   ├── full_heart.csv              # CSV file with patient health records
│
│── notebooks/                     
│   ├── heart_analysis.ipynb        # Data analysis and preprocessing
│   ├── model_training.ipynb        # Model training with Grid Search
│
│── cloud/
│   ├── snowflake_setup.sql         # SQL script for creating Snowflake warehouse
│   ├── aws_s3_snowflake.md         # Documentation on AWS S3 & Snowflake integration
│
│── scripts/
│   ├── snowflake_connection.py     # Connect Snowflake with Python
│   ├── s3_to_snowflake.py          # Load data from S3 to Snowflake
│
│── README.md                       # Project documentation



## Dataset Overview

The dataset contains patient health records, where each row represents a patient with various medical attributes. The target variable is a binary label indicating whether the person has heart disease (1) or not (0).

Data Quality Assurance

The dataset is 100% accurate, with no missing values.
The labels have been validated by three medical specialists, ensuring the reliability of the training data.
No additional preprocessing is required before analysis.

The dataset contains patient health records.
Target variable: 1 = Heart Disease, 0 = No Heart Disease.

Feature	Description
age	Age of the patient
sex	Gender (1 = Male, 0 = Female)
race	Race/Ethnicity of the patient
cp	Chest pain type (categorical)
trestbps	Resting blood pressure (mm Hg)
chol	Serum cholesterol (mg/dl)
fbs	Fasting blood sugar > 120 mg/dl (1 = True, 0 = False)
restecg	Resting electrocardiographic results
thalach	Maximum heart rate achieved
exang	Exercise-induced angina (1 = Yes, 0 = No)
oldpeak	ST depression induced by exercise relative to rest
slope	Slope of the peak exercise ST segment
ca	Number of major vessels (0–3) colored by fluoroscopy
thal	Thalassemia (categorical: 3 = Normal, 6 = Fixed Defect, 7 = Reversible Defect)
target	1 = Heart Disease, 0 = No Heart Disease


## Technologies Used
AWS S3 – Cloud storage for CSV files
Snowflake – Data warehouse for SQL queries and analysis
SQLAlchemy & Snowflake Connector – Database connection in Python
Jupyter Notebook – Data analysis and ML implementation
Scikit-Learn – ML (kNN, SVM, GridSearchCV)


## Steps to Run the Project
1️⃣ Upload Dataset to AWS S3
2️⃣ Load Data into Snowflake using COPY INTO
3️⃣ Run SQL Queries for Analysis
4️⃣ Connect Snowflake with Python (SQLAlchemy)
5️⃣ Train kNN & SVM Models
6️⃣ Optimize SVM Hyperparameters using GridSearchCV
7️⃣ Save the Best Model

##Machine Learning Process
🔹 1. Data Splitting

We use Scikit-Learn's train_test_split() function to divide the dataset into training and test sets.

Random State = 380 ensures repeatability, meaning that after reshuffling, the same data points remain in the same split for every run.
🔹 2. kNN Classification

First, we apply k-Nearest Neighbors (kNN) with n_neighbors = 5.
The model achieves an accuracy of 67%, evaluated using precision, recall, and F1-score.
✅ Hyperparameter Tuning for kNN

Changing n_neighbors = 7 improves accuracy to 71%.
The reason for improvement:
The dataset is slightly biased towards the positive label.
Increasing the number of neighbors reduces overfitting and leads to a better classification boundary.
This demonstrates how hyperparameter tuning impacts accuracy.
🔹 3. Switching to SVM (SVC)

We then apply Support Vector Machine (SVC), which achieves a higher accuracy of 85%.
Since SVM outperforms kNN, we focus on optimizing SVM hyperparameters.
🔹 4. Grid Search for Best Hyperparameters

We use GridSearchCV to fine-tune the SVM model.

Parameters tuned:
C (Regularization parameter)
Kernel (Linear, RBF, Polynomial)
Gamma (Kernel coefficient)
✅ Cross-Validation Strategy

We set cv=2 in GridSearchCV, meaning:
The dataset is split 50% train / 50% test, and
Accuracy is calculated twice, taking the mean result.
This ensures every data point is used for both training and testing.
✅ Final Model

After finding the best hyperparameters, we train the SVM model with optimal parameters and save it as the final model.

