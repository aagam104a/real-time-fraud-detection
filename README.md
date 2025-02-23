"""# Real-Time Fraud Detection in Financial Transactions

## Overview
This project implements a **real-time anomaly detection system** for financial transactions using **Kafka, PySpark, Scikit-learn, AWS Lambda, and Elasticsearch**. The goal is to detect fraudulent transactions in real-time and store flagged transactions for further investigation.

## Tech Stack
- **Kafka** - Streams real-time transaction data.
- **PySpark** - Processes transactions and extracts features.
- **Scikit-learn** - Trains an Isolation Forest model for anomaly detection.
- **AWS Lambda** - Deploys a lightweight fraud detection API.
- **Elasticsearch** - Stores flagged fraudulent transactions for analysis.
- **Streamlit** - Provides a web dashboard for monitoring.

## Project Architecture
1. **Kafka Producer** streams transaction data in real-time.
2. **Spark Streaming** processes the transactions and extracts relevant features.
3. **ML Model** (Isolation Forest) detects anomalies.
4. **AWS Lambda** deploys the fraud detection function as an API.
5. **Elasticsearch** stores fraud alerts for search and visualization.
6. **Streamlit Dashboard** visualizes flagged transactions.

## Project Structure
real-time-fraud-detection/ │── data/ # Dataset and processed data │── kafka/ # Kafka producer for transaction data │── spark/ # Spark streaming for feature extraction │── model/ # ML model training and prediction │── lambda/ # AWS Lambda fraud detection API │── elasticsearch/ # Fraud transaction storage │── dashboard/ # Frontend monitoring (Streamlit) │── deployment/ # Deployment scripts (Docker, AWS) │── tests/ # Unit and integration tests │── notebooks/ # Jupyter notebooks for data analysis │── README.md # Project documentation │── requirements.txt # Dependencies │── .gitignore # Ignore unnecessary files
