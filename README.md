# 🚀 End-to-End MLOps Pipeline with AWS, DVC, MLflow, Docker & Kubernetes

> A production-ready MLOps project demonstrating the complete machine learning lifecycle—from data ingestion to model deployment on Amazon EKS using modern DevOps and MLOps best practices.

![Python](https://img.shields.io/badge/Python-3.10-blue)
![MLflow](https://img.shields.io/badge/MLflow-Experiment%20Tracking-orange)
![DVC](https://img.shields.io/badge/DVC-Data%20Versioning-purple)
![AWS](https://img.shields.io/badge/AWS-EKS%20%7C%20S3%20%7C%20ECR-yellow)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue)
![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-black)

---

# 📌 Project Overview

This repository demonstrates how to build and deploy a **production-grade Machine Learning application** following modern **MLOps practices**.

The project covers the complete ML lifecycle including:

* Data Versioning using **DVC**
* Experiment Tracking using **MLflow (Dagshub)**
* Modular ML Pipeline
* Model Registration
* Flask-based Inference API
* Docker Containerization
* CI/CD using GitHub Actions
* AWS ECR for Image Registry
* Kubernetes Deployment using Amazon EKS

---

# 🏗️ Project Architecture

```text
GitHub Repository
        │
        ▼
GitHub Actions (CI/CD)
        │
        ▼
Docker Build
        │
        ▼
Amazon ECR
        │
        ▼
Amazon EKS Cluster
        │
        ▼
Flask Inference API
        │
        ▼
Prediction Endpoint
```

Training Pipeline

```text
Raw Data
    │
    ▼
Data Ingestion
    │
    ▼
Preprocessing
    │
    ▼
Feature Engineering
    │
    ▼
Model Training
    │
    ▼
Evaluation
    │
    ▼
Model Registration
```

Experiment Tracking

```text
Training
    │
    ▼
MLflow (Dagshub)
        │
        ├── Parameters
        ├── Metrics
        ├── Artifacts
        └── Registered Models
```

---

# ✨ Features

* Modular project structure
* Cookiecutter Data Science template
* DVC pipeline automation
* MLflow experiment tracking
* Model Registry integration
* AWS S3 as DVC remote storage
* Flask REST API
* Dockerized application
* GitHub Actions CI/CD
* Amazon ECR image deployment
* Kubernetes deployment using Amazon EKS

---

# 🛠️ Tech Stack

### Programming

* Python 3.10

### Machine Learning

* Scikit-Learn
* NumPy

### MLOps

* DVC
* MLflow
* Dagshub

### Cloud

* AWS S3
* AWS ECR
* Amazon EKS
* IAM

### DevOps

* Docker
* GitHub Actions
* Kubernetes
* kubectl
* eksctl

---

# 📂 Project Structure

```text
.
├── src
│   ├── logger.py
│   ├── data_ingestion.py
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── model_building.py
│   ├── model_evaluation.py
│   └── register_model.py
│
├── flask_app
│
├── tests
│
├── scripts
│
├── dvc.yaml
├── params.yaml
├── requirements.txt
├── Dockerfile
└── .github/workflows
```

---

# ⚙️ Getting Started

## 1. Clone the Repository

```bash
git clone <repository-url>
cd <repository-name>
```

---

## 2. Create Conda Environment

```bash
conda create -n atlas python=3.10
conda activate atlas
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🧪 MLflow Setup (Dagshub)

1. Create a Dagshub account.
2. Connect your GitHub repository.
3. Copy the MLflow tracking URI.
4. Install:

```bash
pip install dagshub mlflow
```

5. Configure the tracking URI and authentication token.

---

# 📦 Data Versioning with DVC

Initialize DVC

```bash
dvc init
```

Local Remote

```bash
dvc remote add -d mylocal local_s3
```

Run Pipeline

```bash
dvc repro
```

Check Pipeline Status

```bash
dvc status
```

---

# ☁️ Configure AWS S3 as DVC Remote

Install dependencies

```bash
pip install "dvc[s3]" awscli
```

Configure AWS

```bash
aws configure
```

Add S3 Remote

```bash
dvc remote add -d myremote s3://<bucket-name>
```

Push Data

```bash
dvc push
```

---

# 🌐 Flask Inference API

Run the application

```bash
cd flask_app
python app.py
```

---

# 🐳 Docker

Build Image

```bash
docker build -t capstone-app:latest .
```

Run Container

```bash
docker run -p 8888:5000 capstone-app:latest
```

Run with Environment Variables

```bash
docker run -p 8888:5000 \
-e CAPSTONE_TEST=<your-token> \
capstone-app:latest
```

---

# 🔄 CI/CD Pipeline

GitHub Actions automatically performs:

* Install dependencies
* Execute tests
* Build Docker image
* Push image to Amazon ECR

Required GitHub Secrets

* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY
* AWS_REGION
* AWS_ACCOUNT_ID
* ECR_REPOSITORY
* DAGSHUB_TOKEN

---

# ☸️ Deploy to Amazon EKS

Create Cluster

```bash
eksctl create cluster \
--name flask-app-cluster \
--region us-east-1 \
--nodegroup-name flask-app-nodes \
--node-type t3.small \
--nodes 1
```

Update kubeconfig

```bash
aws eks update-kubeconfig \
--region us-east-1 \
--name flask-app-cluster
```

Verify Cluster

```bash
kubectl get nodes
```

Delete Cluster

```bash
eksctl delete cluster \
--name flask-app-cluster \
--region us-east-1
```

---

# 📊 Workflow

```text
GitHub
    │
    ▼
GitHub Actions
    │
    ▼
Docker Build
    │
    ▼
Amazon ECR
    │
    ▼
Amazon EKS
    │
    ▼
Flask API
```

Training Workflow

```text
Data
  │
  ▼
Ingestion
  │
  ▼
Preprocessing
  │
  ▼
Feature Engineering
  │
  ▼
Training
  │
  ▼
Evaluation
  │
  ▼
MLflow + DVC
```

---

# 🎯 Learning Outcomes

This project demonstrates practical experience with:

* End-to-End MLOps
* Production ML Pipelines
* Experiment Tracking
* Data Versioning
* Model Registry
* Cloud Deployment
* Docker
* Kubernetes
* AWS Services
* CI/CD Automation

---

# ⭐ If you found this project useful

Consider giving the repository a ⭐ to support the project!
