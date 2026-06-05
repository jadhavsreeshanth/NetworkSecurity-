# Network Security Threat Detection

A machine learning project for detecting phishing-based network security threats from structured network traffic features. The project follows an end-to-end ML pipeline design, including data ingestion, validation, transformation, model training, experiment tracking, and web-based prediction.

## Overview

Phishing and malicious network activity can often be identified from traffic-level patterns such as URL behavior, redirection, domain age, SSL state, request structure, and other security-related indicators. This project uses supervised machine learning to classify network records as legitimate or suspicious.

The system is designed as a modular pipeline so that each stage of the workflow can be maintained, debugged, and reused independently.

## Key Features

- End-to-end machine learning pipeline for phishing threat detection
- Data ingestion from MongoDB
- Data validation using schema checks and data drift reports
- Missing value handling and feature transformation
- Model training with multiple classification algorithms
- Model evaluation using precision, recall, F1-score, and accuracy
- Experiment tracking with MLflow and DagsHub
- FastAPI-based web application for predictions
- Saved model and preprocessor artifacts for inference

## Tech Stack

- Python
- MongoDB
- pandas
- NumPy
- scikit-learn
- FastAPI
- MLflow
- DagsHub
- PyYAML
- Dill

## Machine Learning Models

The training pipeline compares multiple classification models and selects the best performing model based on evaluation metrics.

Models used:

- Random Forest
- Gradient Boosting
- AdaBoost
- Logistic Regression
- Decision Tree

## Performance

The best model achieved strong classification performance:

| Metric | Score |
| --- | ---: |
| F1-score | 0.974 |
| Precision | 0.962 |
| Recall | 0.986 |

## Project Workflow

```text
MongoDB / Dataset
        |
        v
Data Ingestion
        |
        v
Data Validation
        |
        v
Data Transformation
        |
        v
Model Training
        |
        v
Model Evaluation
        |
        v
Saved Model Artifacts
        |
        v
FastAPI Prediction App
```

## Project Structure

```text
NetworkSecurity/
├── README.md
├── app.py
├── main.py
├── push_data.py
├── setup.py
├── data_schema/
│   └── schema.yaml
├── networksecurity/
│   ├── components/
│   ├── constant/
│   ├── entity/
│   ├── exception/
│   ├── logging/
│   ├── pipeline/
│   └── utils/
├── Network_Data/
├── valid_data/
├── final_model/
├── templates/
```

## Installation

Clone the repository:

```bash
git clone https://github.com/jadhavsreeshanth/NetworkSecurity-.git
cd NetworkSecurity
```

Create and activate a virtual environment:

```bash
python -m venv venv
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Environment Variables

Create a `.env` file or set the MongoDB connection string in your terminal:

```bash
MONGODB_URL_KEY="your_mongodb_connection_string"
```

For Windows PowerShell:

```powershell
$env:MONGODB_URL_KEY="your_mongodb_connection_string"
```

## Run Training Pipeline

```bash
python main.py
```

This runs the complete pipeline:

1. Data ingestion
2. Data validation
3. Data transformation
4. Model training
5. Model artifact generation

## Run Prediction App

```bash
python app.py
```

After starting the app, open:

```text
http://127.0.0.1:8000
```

## Dataset

The dataset contains phishing-related network and URL features such as:

- `having_IP_Address`
- `URL_Length`
- `Shortining_Service`
- `SSLfinal_State`
- `Domain_registeration_length`
- `HTTPS_token`
- `Submitting_to_email`
- `web_traffic`
- `Page_Rank`
- `Google_Index`
- `Statistical_report`



## Author

Jadhav Sreeshanth
