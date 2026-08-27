# Big Data Cybersecurity Threat Detection

> A scalable cybersecurity analytics platform that uses **Apache Spark, Big Data processing, and Machine Learning** to detect and analyze malicious network activity from large-scale network traffic data.

![Python](https://img.shields.io/badge/Python-3.14-blue)
![Apache Spark](https://img.shields.io/badge/Apache%20Spark-4.2-orange)
![Java](https://img.shields.io/badge/Java-21-red)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-green)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-FF4B4B)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## Overview

Cybersecurity systems generate enormous volumes of network and security logs every day. Traditional single-machine processing can become inefficient when dealing with large-scale security data.

This project develops a **Big Data-based cybersecurity threat detection system** capable of processing large network traffic datasets, extracting meaningful security features, identifying suspicious activity, and presenting the results through an interactive dashboard.

The system uses **Apache Spark/PySpark** for distributed data processing and **Machine Learning** for threat classification.

The initial dataset used in the project is **UNSW-NB15**, which contains normal network traffic as well as multiple categories of malicious activity.

---

## Objectives

The major objectives of this project are:

* Process large-scale cybersecurity datasets efficiently.
* Use Apache Spark for distributed data processing.
* Perform data cleaning and preprocessing.
* Engineer useful network security features.
* Identify normal and malicious network traffic.
* Classify different categories of cyber attacks.
* Store processed security results.
* Provide an interactive cybersecurity analytics dashboard.
* Evaluate machine learning performance using appropriate metrics.
* Demonstrate an end-to-end Big Data and Machine Learning workflow.

---

## System Architecture

```text
                    ┌──────────────────────┐
                    │   UNSW-NB15 Dataset  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Data Ingestion    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      HDFS / Storage  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │       PySpark        │
                    │  Data Processing     │
                    └──────────┬───────────┘
                               │
                     ┌─────────┴─────────┐
                     ▼                   ▼
              Data Cleaning      Feature Engineering
                     │                   │
                     └─────────┬─────────┘
                               ▼
                    ┌──────────────────────┐
                    │     Spark MLlib      │
                    │ Threat Classification│
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │       MongoDB        │
                    │   Results Storage    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │ Streamlit Dashboard  │
                    │ Security Analytics   │
                    └──────────────────────┘
```

---

## 🔍 Cybersecurity Threats

The UNSW-NB15 dataset contains several categories of network activity.

The project can analyze categories including:

| Category       | Description                          |
| -------------- | ------------------------------------ |
| Normal         | Legitimate network activity          |
| DoS            | Denial-of-Service activity           |
| Exploits       | Exploitation of vulnerabilities      |
| Fuzzers        | Fuzzing-based attacks                |
| Reconnaissance | Network/system information gathering |
| Generic        | Generic attack patterns              |
| Shellcode      | Shellcode-based attacks              |
| Worms          | Worm propagation activity            |
| Backdoors      | Unauthorized backdoor activity       |

---

## Technology Stack

### Big Data

* **Apache Spark 4.2**
* **PySpark**
* Hadoop / HDFS

### Programming

* **Python 3.14**
* **Java 21**

### Machine Learning

* Spark MLlib
* Scikit-learn

### Database

* MongoDB

### Visualization

* Streamlit
* Pandas
* Matplotlib

### Development & DevOps

* Git
* GitHub
* Docker
* Jenkins

---

## Project Structure

```text
cybersecurity-threat-detection/
│
├── data/
│   └── raw/
│       └── UNSW-NB15 dataset files
│
├── spark/
│   ├── inspect_data.py
│   ├── preprocess.py
│   ├── feature_engineering.py
│   └── train_model.py
│
├── ml/
│   └── model/
│
├── mongodb/
│   └── store_results.py
│
├── dashboard/
│   └── app.py
│
├── hdfs/
│
├── run_pipeline.py
│
├── requirements.txt
├── .gitignore
└── README.md
```

> **Note:** Large raw datasets are intentionally excluded from GitHub using `.gitignore`.

---

## 📊 Data Processing Pipeline

The project follows a multi-stage Big Data processing pipeline.

### 1. Data Ingestion

Large cybersecurity datasets are loaded into the processing environment.

### 2. Data Cleaning

The raw network data is processed to:

* Handle missing values
* Remove unnecessary fields
* Correct data types
* Remove duplicate records
* Prepare data for machine learning

### 3. Feature Engineering

Network traffic attributes are transformed into machine-learning-ready features.

Example features include:

* Source/destination information
* Network protocol
* Connection duration
* Packet counts
* Byte counts
* Traffic rates
* Connection statistics
* Attack labels

### 4. Distributed Processing

PySpark processes the dataset using Spark's distributed DataFrame and SQL capabilities.

### 5. Machine Learning

The processed data is used to train classification/anomaly detection models.

Potential models include:

* Random Forest
* Decision Tree
* Logistic Regression
* Gradient Boosting
* Isolation Forest

### 6. Result Storage

Threat detection results are stored in MongoDB for further analysis.

### 7. Dashboard

Streamlit provides an interactive interface for monitoring cybersecurity activity.

---

## 📈 Dashboard

The planned dashboard will provide real-time or batch security analytics such as:

* Total network events
* Normal traffic count
* Malicious traffic count
* Attack percentage
* Attack category distribution
* Most frequent attack types
* Suspicious network activity
* Traffic trends
* Model performance
* Detection statistics

Example dashboard sections:

```text
┌─────────────────────────────────────────────────────┐
│             CYBERSECURITY DASHBOARD                 │
├─────────────────────────────────────────────────────┤
│ Total Events │ Normal │ Threats │ Threat Rate       │
├─────────────────────────────────────────────────────┤
│                                                     │
│        Attack Distribution Chart                    │
│                                                     │
├─────────────────────────────────────────────────────┤
│                                                     │
│        Threat Activity Over Time                    │
│                                                     │
├─────────────────────────────────────────────────────┤
│ Top Threat Categories │ Suspicious Activity         │
└─────────────────────────────────────────────────────┘
```

---

## 🤖 Machine Learning Evaluation

The machine learning component will be evaluated using metrics appropriate for cybersecurity classification.

Primary metrics include:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* ROC-AUC
* PR-AUC

Because cybersecurity datasets can be highly imbalanced, **Precision, Recall, F1-score, and PR-AUC** will receive particular attention rather than relying only on accuracy.

---

## Installation

### Prerequisites

Make sure the following are installed:

* Python 3.14+
* Java JDK 21
* Apache Spark
* Hadoop/HDFS
* MongoDB

### Clone the repository

```bash
git clone https://github.com/tarrsvijay-dot/cybersecurity-threat-detection.git
cd cybersecurity-threat-detection
```

### Create a virtual environment

Windows:

```cmd
python -m venv venv
venv\Scripts\activate
```

### Install dependencies

```cmd
pip install -r requirements.txt
```

---

##Running the Project

### Run the Spark data inspection

```cmd
python spark/inspect_data.py
```

### Run preprocessing

```cmd
python spark/preprocess.py
```

### Run feature engineering

```cmd
python spark/feature_engineering.py
```

### Train the model

```cmd
python spark/train_model.py
```

### Start the dashboard

```cmd
streamlit run dashboard/app.py
```

---

## 🧪 Example Workflow

```text
Raw Dataset
     ↓
Data Cleaning
     ↓
Feature Engineering
     ↓
Distributed Spark Processing
     ↓
Machine Learning
     ↓
Threat Prediction
     ↓
MongoDB
     ↓
Security Dashboard
```

---

##Security Considerations

This project is intended for **defensive cybersecurity research and educational purposes**.

The system focuses on:

* Detecting suspicious activity
* Network traffic analysis
* Security monitoring
* Anomaly detection
* Threat classification

It does not provide functionality for conducting attacks against real systems.

---

##Dataset

### UNSW-NB15

The UNSW-NB15 dataset was developed by the **Australian Centre for Cyber Security (ACCS)** at UNSW Canberra.

It contains realistic network traffic and multiple categories of malicious activity.

Official dataset information:

https://research.unsw.edu.au/projects/unsw-nb15-dataset

---

##Development Roadmap

### Phase 1 — Environment Setup

* [x] Python environment
* [x] Java JDK
* [x] PySpark installation
* [x] SparkSession verification
* [x] GitHub repository

### Phase 2 — Data Engineering

* [ ] Download dataset
* [ ] Load data using PySpark
* [ ] Data cleaning
* [ ] Exploratory analysis
* [ ] Feature engineering
* [ ] HDFS integration

### Phase 3 — Machine Learning

* [ ] Prepare training data
* [ ] Train baseline model
* [ ] Train advanced models
* [ ] Compare models
* [ ] Evaluate performance
* [ ] Save trained model

### Phase 4 — Storage & Dashboard

* [ ] MongoDB integration
* [ ] Store prediction results
* [ ] Build Streamlit dashboard
* [ ] Add security visualizations
* [ ] Add model metrics

### Phase 5 — Advanced Features

* [ ] Kafka integration
* [ ] Spark Streaming
* [ ] Real-time threat detection
* [ ] Docker deployment
* [ ] Jenkins CI/CD
* [ ] Cloud deployment

---

**Future Enhancements**

The project can be extended into a real-time security monitoring platform by integrating:

* Apache Kafka for real-time event ingestion
* Spark Structured Streaming
* Real-time anomaly detection
* Automated security alerts
* Docker containers
* Jenkins CI/CD
* Cloud infrastructure
* Role-based dashboard access
* Advanced threat intelligence

---

**Author**

**Tarrsan Vijay**

Software Engineering Student
VIT Vellore, India

GitHub:
https://github.com/tarrsvijay-dot

---

**License**

This project is developed for **academic and educational purposes**.

The UNSW-NB15 dataset is subject to its respective terms of use and licensing conditions.

---

## Project Status

**🚧 Active Development**

The project is currently under development. Features will be added progressively as the Big Data processing, Machine Learning, database, and dashboard components are implemented.
