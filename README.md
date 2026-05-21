# ZENTRIX — Multimodal AI-Powered Industrial Worker Health & Safety Monitoring System

## Project Overview

ZENTRIX is a Machine Learning and Multimodal AI-based industrial worker monitoring system designed to improve workplace safety, health assessment, and operational efficiency in industrial environments.

The project focuses on analyzing worker-related health and safety parameters using multiple Machine Learning algorithms to predict risk levels, monitor PPE compliance, and generate intelligent safety insights.

The system is inspired by real-world industrial safety challenges where workers are exposed to:
- Unsafe working environments
- PPE violations
- Fatigue and health risks
- Hazardous operational conditions
- Workplace accidents and injuries

The project aims to build an AI-powered intelligent monitoring system capable of supporting proactive industrial safety management.

---

# Problem Statement

Industrial workplaces such as factories, manufacturing units, and construction sites are highly vulnerable to:
- Workplace injuries
- Unsafe practices
- Occupational health hazards
- PPE violations
- Health-related emergencies

Traditional monitoring systems often rely on:
- Manual inspections
- CCTV surveillance only
- Periodic health checkups

These approaches fail to provide real-time integrated monitoring of worker health and safety.

ZENTRIX addresses this challenge by integrating Machine Learning and Multimodal AI techniques to:
- Monitor worker safety
- Detect unsafe conditions
- Analyze health-related indicators
- Predict risk levels
- Support intelligent industrial monitoring

---

# Objectives

- Improve industrial worker safety
- Predict workplace risk levels
- Monitor PPE compliance
- Analyze worker health indicators
- Apply Machine Learning algorithms for intelligent prediction
- Build a scalable AI-driven safety monitoring system

---

# Technologies Used

## Programming Language
- Python

## Libraries & Frameworks
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Joblib

---

# Dataset Preprocessing

The following preprocessing steps were performed in the notebook:

### 1. Dataset Loading
```python
df = pd.read_excel("worker_health_dataset.xlsx")
```

### 2. Removed Unnecessary Columns
```python
df.drop([
    "worker_id",
    "reported_symptoms",
    "diagnosis",
    "outcome"
], axis=1)
```

### 3. One-Hot Encoding
Applied on:
- department
- risk_level

```python
pd.get_dummies(df,
               columns=["department","risk_level"],
               drop_first=True)
```

---

# Features Used

The project dataset contains worker-related industrial and healthcare features such as:

- Age
- Department
- Shift Duration
- PPE Compliance Score
- Risk Levels
- Health Indicators
- Audio Alert Flags
- Industrial Monitoring Parameters

---

# Machine Learning Models Implemented

The project includes multiple Machine Learning algorithms for:
- Regression
- Classification
- Clustering

---

# 1. Linear Regression

## Purpose
Used for predicting PPE compliance score and performing regression analysis.

## Implementation
```python
from sklearn.linear_model import LinearRegression
```

## Evaluation Metrics

| Metric | Value |
|---|---|
| Mean Squared Error (MSE) | 0.00978559009543734 |
| R² Score | 0.7896926017698318 |

---

# 2. Logistic Regression

## Purpose
Used for classification-based worker risk prediction.

## Implementation
```python
from sklearn.linear_model import LogisticRegression
```

## Accuracy
```text
98.33%
```

---

# 3. Decision Tree Classifier

## Purpose
Used for identifying industrial safety patterns and worker risk categories.

## Implementation
```python
from sklearn.tree import DecisionTreeClassifier
```

## Accuracy
```text
99.66%
```

---

# 4. Support Vector Machine (SVM)

## Purpose
Used for high-performance classification with feature scaling.

## Implementation
```python
from sklearn.svm import SVC
```

## Feature Scaling
```python
StandardScaler()
```

## Accuracy
```text
99.00%
```

---

# 5. Random Forest Classifier

## Purpose
Used for ensemble-based worker risk prediction and safety classification.

## Implementation
```python
from sklearn.ensemble import RandomForestClassifier
```

## Accuracy
```text
99.33%
```

---

# 6. K-Means Clustering

## Purpose
Used for unsupervised clustering of worker safety and risk-related patterns.

## Implementation
```python
from sklearn.cluster import KMeans
```

## Configuration
```python
KMeans(n_clusters=3, random_state=42)
```

## Output
The model generated worker clusters based on industrial safety parameters.

---

# 7. Gaussian Naive Bayes

## Purpose
Used for probabilistic classification using Gaussian distribution assumptions.

## Implementation
```python
from sklearn.naive_bayes import GaussianNB
```

## Workflow
- Model Training
- Prediction
- Accuracy Evaluation

---

# 8. Multinomial Naive Bayes

## Purpose
Used for comparative probabilistic classification analysis.

## Implementation
```python
from sklearn.naive_bayes import MultinomialNB
```

## Workflow
- Model Training
- Prediction
- Accuracy Comparison with GaussianNB

---

# 9. K-Nearest Neighbors (KNN)

## Purpose
Used for distance-based worker risk classification.

## Implementation
```python
from sklearn.neighbors import KNeighborsClassifier
```

## Configuration
```python
KNeighborsClassifier(n_neighbors=10)
```

---

# Model Performance Summary

| Model | Type | Accuracy / Score |
|---|---|---|
| Linear Regression | Regression | R² = 0.7896 |
| Logistic Regression | Classification | 98.33% |
| Decision Tree Classifier | Classification | 99.66% |
| Support Vector Machine (SVM) | Classification | 99.00% |
| Random Forest Classifier | Classification | 99.33% |
| Gaussian Naive Bayes | Classification | Implemented |
| Multinomial Naive Bayes | Classification | Implemented |
| K-Nearest Neighbors (KNN) | Classification | Implemented |
| K-Means Clustering | Clustering | Implemented |

---

# Train-Test Split

The dataset was split into:
- 80% Training Data
- 20% Testing Data

```python
train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

---

# Model Serialization

The project uses Joblib for model saving.

## Saved Models
```python
joblib.dump(gnb,'zentrix_gnb')
joblib.dump(mnb,'zentrix_mnb')
```

---

# System Workflow

## Step 1 — Data Collection
Collect industrial worker health and safety data.

## Step 2 — Data Preprocessing
- Cleaning
- Feature selection
- Encoding

## Step 3 — Feature Engineering
Prepare input features for ML models.

## Step 4 — Model Training
Train multiple ML algorithms.

## Step 5 — Model Evaluation
Compare model performances using:
- Accuracy
- MSE
- R² Score

## Step 6 — Risk Prediction
Generate worker safety predictions and classifications.

---

# Key Features

- Industrial worker monitoring
- PPE compliance analysis
- Health and safety risk prediction
- Multiple Machine Learning models
- Classification and clustering
- Intelligent industrial analytics
- AI-powered safety assessment

---

# Expected Outcomes

- Reduce workplace accidents
- Improve industrial safety monitoring
- Enable intelligent decision-making
- Support proactive healthcare monitoring
- Build scalable AI-based industrial systems

---

# Future Enhancements

- Real-time CCTV integration
- Audio distress signal detection
- Computer Vision implementation
- Deep Learning models
- IoT sensor integration
- Live dashboard deployment
- Cloud-based MLOps pipeline
- Real-time alert system

---

# Conclusion

ZENTRIX demonstrates the practical application of Machine Learning and Multimodal AI in industrial worker health and safety monitoring.

By integrating:
- Classification models
- Clustering algorithms
- Regression analysis
- Industrial safety analytics

the project creates a strong foundation for intelligent workplace monitoring systems capable of improving worker safety, operational efficiency, and healthcare monitoring in industrial environments.

---
