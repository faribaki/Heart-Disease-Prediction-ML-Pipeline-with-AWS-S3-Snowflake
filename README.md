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

