# DDoS Attack Detection using Supervised Machine Learning

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange)
![Cybersecurity](https://img.shields.io/badge/Domain-Cybersecurity-red)
![Status](https://img.shields.io/badge/Project-Academic-green)

---

# Project Overview

Distributed Denial-of-Service (**DDoS**) attacks are among the most serious threats to modern network infrastructures. These attacks flood a target server with massive traffic from multiple compromised systems, making services unavailable to legitimate users.

This project proposes a **PCA-Based Enhanced Distributed DDoS Attack Detection (EDAD) framework** that uses **supervised machine learning algorithms** to identify malicious network traffic.

The system analyzes network flow features and classifies traffic as **benign or attack traffic** using multiple machine learning models.

---

# Research Objective

The objective of this project is to:

- Detect **DDoS attacks in network traffic**
- Compare the performance of different **supervised ML algorithms**
- Improve detection accuracy using **feature selection and preprocessing**
- Apply **model interpretability techniques (SHAP)**

---

# Datasets Used

This project uses publicly available datasets from the **Canadian Institute for Cybersecurity (CIC)**.

### 1️⃣ CICIDS2017
Contains realistic network traffic with multiple cyber attack types.

Attack examples:
- DDoS
- DoS
- Brute Force
- Web attacks
- Port scanning

Dataset link  
https://www.unb.ca/cic/datasets/ids-2017.html

---

### 2️⃣ CICIDS2018

An updated dataset with more modern attack scenarios.

Includes:
- Botnet attacks
- DDoS attacks
- Web attacks
- Brute-force attacks

Dataset link  
https://www.unb.ca/cic/datasets/ids-2018.html

---

### 3️⃣ CICDDoS2019

A dataset designed specifically for **DDoS detection**.

Includes attack types such as:

- SYN Flood
- UDP Flood
- DNS Amplification
- LDAP Attack
- NTP Amplification

Dataset link  
https://www.unb.ca/cic/datasets/ddos-2019.html

---

# System Architecture

```
Network Traffic Dataset
        │
        ▼
Data Preprocessing
(Remove duplicates, missing values)
        │
        ▼
Label Encoding
        │
        ▼
Feature Scaling (StandardScaler)
        │
        ▼
Handling Class Imbalance (SMOTE)
        │
        ▼
Feature Selection (PCA)
        │
        ▼
Machine Learning Models
│      │       │      │       │
RF     LR      KNN    SVM     DT
        │
        ▼
Model Evaluation
        │
        ▼
Explainability (SHAP)
```

---

# Data Preprocessing

Several preprocessing techniques were applied to improve dataset quality:

- Removing **missing values**
- Removing **duplicate records**
- Handling **infinite values**
- Data normalization using **StandardScaler**
- **Label encoding** for categorical classes

The original **79 features were reduced to 61 useful features** after preprocessing.

---

# Handling Class Imbalance

Cybersecurity datasets are often **imbalanced**, where benign traffic dominates attack samples.

To address this issue:

**SMOTE (Synthetic Minority Oversampling Technique)** was applied to generate synthetic attack samples and balance the dataset.

---

# Feature Selection

**Principal Component Analysis (PCA)** was used for dimensionality reduction.

Benefits:

- Reduces feature redundancy
- Improves model efficiency
- Reduces noise
- Retains maximum variance

---

# Machine Learning Models

The following supervised machine learning algorithms were implemented:

| Algorithm | Description |
|----------|-------------|
| Random Forest | Ensemble learning method using multiple decision trees |
| Logistic Regression | Probabilistic classification model |
| K-Nearest Neighbors (KNN) | Distance-based classification |
| Support Vector Machine (SVM) | Maximum margin classifier |
| Decision Tree | Tree-based interpretable model |

---

# Evaluation Metrics

Model performance was evaluated using:

| Metric | Description |
|------|-------------|
| Accuracy | Overall prediction correctness |
| Precision | Correct positive predictions |
| Recall | Ability to detect attacks |
| F1 Score | Balance between precision and recall |

These metrics were calculated using the **confusion matrix**.

---

# Experimental Results

## CICIDS2017 Dataset

| Model | Accuracy |
|------|---------|
| Random Forest | 0.999397 |
| Logistic Regression | 0.994237 |
| KNN | **0.999464** |
| SVM | 0.990954 |
| Decision Tree | 0.999129 |

**Best Model:** KNN

---

## CICIDS2018 Dataset

| Model | Accuracy |
|------|---------|
| Random Forest | 0.999791 |
| Logistic Regression | 0.995048 |
| KNN | **0.999930** |
| SVM | 0.998187 |
| Decision Tree | 0.999582 |

**Best Model:** KNN

---

## CICDDoS2019 Dataset

| Model | Accuracy |
|------|---------|
| Random Forest | **0.984733** |
| Logistic Regression | 0.973533 |
| KNN | 0.972600 |
| SVM | 0.969533 |
| Decision Tree | 0.979800 |

**Best Model:** Random Forest

---

# Model Explainability

To improve interpretability, two techniques were used:

### Decision Tree Feature Importance

Identifies the most influential network traffic features used in classification.

### SHAP (SHapley Additive Explanations)

SHAP explains model predictions by measuring the contribution of each feature to the final output.

This helps understand **why a network flow is classified as malicious or benign**.

---

# Technologies Used

### Programming Language

- Python

### Libraries

- NumPy
- Pandas
- Scikit-learn
- Imbalanced-learn
- Matplotlib
- Seaborn
- SHAP

---

# Installation

Clone the repository

```bash
git clone https://github.com/RishiRaajhaA/DDoS-Attack-Detection-ML.git
cd DDoS-Attack-Detection-ML
```

Install dependencies

```bash
pip install numpy pandas scikit-learn imbalanced-learn matplotlib seaborn shap
```

Run Jupyter Notebook

```bash
jupyter notebook
```

Open the notebooks

```
ddos_pca_edad2017.ipynb
ddos_pca_edad2018.ipynb
ddos_pca_edad2019.ipynb
```

---

# Future Improvements

Future research directions include:

- Deep learning models such as **CNN, LSTM, and RNN**
- Real-time DDoS detection systems
- Integration with **network monitoring tools**
- Deployment using **Flask or FastAPI**
- Real-time IDS for cloud environments

---

# Authors

- **Rishi Raajha A**
- Naveen Sankar R S
- Sakthi Pranav S
- Harshvardhan V

Department of Artificial Intelligence  
Amrita Vishwa Vidyapeetham, Coimbatore

---

# Academic Information

Course: **Computer Security (22AIE314)**  
Supervisor: **Dr. Vipin Das**  
Amrita School of Artificial Intelligence

---

# License

This project is developed for **academic and research purposes**.
