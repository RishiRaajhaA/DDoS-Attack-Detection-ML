# DDoS Attack Detection using PCA and Machine Learning

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange)
![Cybersecurity](https://img.shields.io/badge/Domain-Cybersecurity-red)
![License](https://img.shields.io/badge/License-Academic-green)

---

## Project Overview

Distributed Denial-of-Service (**DDoS**) attacks are one of the most serious cybersecurity threats. These attacks overwhelm network resources, causing service disruptions and system downtime.

This project implements a **machine learning-based DDoS detection system** using:

- Exploratory Data Analysis (EDA)
- Data preprocessing and cleaning
- Feature scaling
- Handling class imbalance with **SMOTE**
- Dimensionality reduction using **PCA**
- Training multiple **machine learning models**
- Model explainability using **SHAP**

The system is evaluated on three widely used cybersecurity datasets:

- **CICIDS2017**
- **CICIDS2018**
- **CICDDoS2019**

---

# Repository Structure

```
ddos-detection-pca/
│
├── ddos_pca_edad2017.ipynb
├── ddos_pca_edad2018.ipynb
├── ddos_pca_edad2019.ipynb
│
└── README.md
```

---

# System Architecture

```
Network Traffic Dataset
        │
        ▼
Data Cleaning & Preprocessing
        │
        ▼
Feature Scaling (StandardScaler)
        │
        ▼
Class Imbalance Handling (SMOTE)
        │
        ▼
Dimensionality Reduction (PCA)
        │
        ▼
Machine Learning Models
│       │        │       │
DT     RF       SVM     KNN
        │
        ▼
Model Evaluation
        │
        ▼
Explainability (SHAP)
```

---

# Datasets

This project uses publicly available cybersecurity datasets from the **Canadian Institute for Cybersecurity**.

---

## CICIDS2017

A modern intrusion detection dataset containing realistic network traffic.

Attack types include:

- DDoS
- DoS
- Brute Force
- Web Attacks
- Port Scanning

Dataset link:  
https://www.unb.ca/cic/datasets/ids-2017.html

---

## CICIDS2018

An improved dataset containing updated attack simulations.

Attack types include:

- Botnet attacks
- DDoS attacks
- Brute force attacks
- Web attacks

Dataset link:  
https://www.unb.ca/cic/datasets/ids-2018.html

---

## CICDDoS2019

A dataset specifically designed for **DDoS detection**.

Attack types include:

- SYN Flood
- UDP Flood
- DNS Amplification
- LDAP Attack
- NTP Amplification

Dataset link:  
https://www.unb.ca/cic/datasets/ddos-2019.html

---

# Machine Learning Pipeline

## 1. Data Preprocessing

Steps performed:

- Handling missing values
- Removing duplicate records
- Cleaning invalid feature values

---

## 2. Train-Test Split

The dataset is split into:

- **70% Training Data**
- **30% Testing Data**

---

## 3. Feature Scaling

All features are normalized using **StandardScaler**.

Benefits:

- Prevents bias caused by large feature values
- Improves model convergence
- Required for PCA and distance-based models

---

## 4. Handling Class Imbalance

Cybersecurity datasets are often **highly imbalanced**.

To solve this problem, **SMOTE (Synthetic Minority Oversampling Technique)** is used to generate synthetic samples for the minority class.

---

## 5. Dimensionality Reduction

**Principal Component Analysis (PCA)** is used to reduce feature dimensionality.

PCA retains **95% of the dataset variance**, helping reduce noise and computational cost.

---

# Machine Learning Models

The following machine learning algorithms are trained and evaluated:

| Model | Description |
|------|-------------|
| Decision Tree | Tree-based classification model |
| Random Forest | Ensemble learning method |
| Support Vector Machine | Maximum margin classifier |
| K-Nearest Neighbors | Distance-based classification |
| Logistic Regression | Linear classification model |

---

# Evaluation Metrics

Model performance is evaluated using:

| Metric | Description |
|------|-------------|
| Accuracy | Overall prediction correctness |
| Precision | Correct positive predictions |
| Recall | Ability to detect attacks |
| F1 Score | Balance between precision and recall |

---

# Explainable AI

To interpret model decisions, **SHAP (SHapley Additive Explanations)** is used.

SHAP helps to:

- Understand feature importance
- Explain predictions
- Improve transparency in ML models

---

# Technologies Used

## Programming Language

- Python

## Libraries

- NumPy
- Pandas
- Scikit-learn
- Imbalanced-learn
- Matplotlib
- Seaborn
- SHAP

---

# Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/ddos-detection-pca.git
cd ddos-detection-pca
```

Install dependencies:

```bash
pip install numpy pandas scikit-learn imbalanced-learn matplotlib seaborn shap
```

Run Jupyter Notebook:

```bash
jupyter notebook
```

Open the notebooks:

```
ddos_pca_edad2017.ipynb
ddos_pca_edad2018.ipynb
ddos_pca_edad2019.ipynb
```

---

# Results

The models successfully detect **DDoS attacks using PCA-reduced feature space**.

Key observations:

- PCA significantly reduces feature dimensionality
- Tree-based models perform strongly on network traffic data
- SMOTE improves recall for minority attack classes

---

# Future Improvements

Possible improvements include:

- Deep learning models (CNN, LSTM)
- Real-time network traffic monitoring
- Feature engineering optimization
- Deployment using Flask or FastAPI
- Integration with SIEM tools

---

# Author

**Rishi Raajha A**

Cybersecurity & AI Research Enthusiast

---

# License

This project is intended for **educational and research purposes**.
