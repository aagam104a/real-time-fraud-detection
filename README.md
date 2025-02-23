### Real-Time Fraud Detection in Financial Transactions

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


## Step-by-Step Implementation Guide

### **1. Kafka Setup (Real-time Data Streaming)**
- Set up a Kafka broker using Docker.
- Create a producer (`producer.py`) that sends transaction data.
- Stream synthetic or real transaction data into Kafka.

### **2. PySpark Streaming (Real-time Data Processing)**
- Use Spark Streaming to read transaction data from Kafka.
- Perform feature extraction (e.g., transaction amount, time, location).
- Send processed data for fraud detection.

### **3. Machine Learning Model (Fraud Detection)**
- Use historical transaction data to train an **Isolation Forest** model.
- Train the model using `Scikit-learn` and save it (`fraud_detection_model.pkl`).
- Load and use this model in AWS Lambda for real-time predictions.

### **4. AWS Lambda (Fraud Detection API)**
- Deploy the trained model in an AWS Lambda function.
- Create an API endpoint with API Gateway to return fraud predictions.
- The Lambda function will load the model and classify transactions in real time.

### **5. Elasticsearch (Fraud Storage & Analysis)**
- Set up an **Elasticsearch cluster** to store flagged fraud transactions.
- Integrate fraud alerts into Elasticsearch for quick search and retrieval.

### **6. Streamlit Dashboard (Visualization & Monitoring)**
- Build a **real-time dashboard** to monitor transactions.
- Display **fraud alerts**, **trends**, and **high-risk transactions**.
