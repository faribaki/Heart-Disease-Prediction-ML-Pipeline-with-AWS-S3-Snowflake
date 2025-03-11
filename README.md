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



###Dataset Overview
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


###Technologies Used
AWS S3 – Cloud storage for CSV files
Snowflake – Data warehouse for SQL queries and analysis
SQLAlchemy & Snowflake Connector – Database connection in Python
Jupyter Notebook – Data analysis and ML implementation
Scikit-Learn – ML (kNN, SVM, GridSearchCV)


###Steps to Run the Project
1️⃣ Upload Dataset to AWS S3
2️⃣ Load Data into Snowflake using COPY INTO
3️⃣ Run SQL Queries for Analysis
4️⃣ Connect Snowflake with Python (SQLAlchemy)
5️⃣ Train kNN & SVM Models
6️⃣ Optimize SVM Hyperparameters using GridSearchCV
7️⃣ Save the Best Model

