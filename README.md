# 🩺 Diabetes Prediction Model – Your First MLOps Project (FastAPI + Docker + K8s)

> 🎥 YouTube video for the project: **"Build Your First MLOps Project"**

This project helps you learn **Building and Deploying an ML Model** using a simple and real-world use case: predicting whether a person is diabetic based on health metrics. We’ll go from:

- ✅ Model Training
- ✅ Building the Model locally
- ✅ API Deployment with FastAPI
- ✅ Dockerization
- ✅ Kubernetes Deployment

---

## 📊 Problem Statement

Predict if a person is diabetic based on:
- Pregnancies
- Glucose
- Blood Pressure
- BMI
- Age

We use a Random Forest Classifier trained on the **Pima Indians Diabetes Dataset**.

---

## 🚀 Quick Start

### 1. Clone the Repo

```bash
git clone https://github.com/iam-veeramalla/first-mlops-project.git
cd first-mlops-project
```

### 2. Create Virtual Environment

```
python3 -m venv .mlops
source .mlops/bin/activate
```

### 3. Install Dependencies

```
pip install -r requirements.txt
```

## Train the Model

```
python train.py
```

## Run the API Locally

```
uvicorn main:app --reload
```

### Sample Input for /predict
#### Visit /docs and then you can test predict from there.
```
{
  "Pregnancies": 2,
  "Glucose": 130,
  "BloodPressure": 70,
  "BMI": 28.5,
  "Age": 45
}
```

## Dockerize the API

### Build the Docker Image

```
docker build -t diabetes-prediction-model .
```

### Docker tag and push

```
docker tag diabetes-prediction-model:latest rajathh/diabetes-prediction-model:latest
docker push rajathh/diabetes-prediction-model
```

### Run the Container

```
docker run -p 8000:8000 diabetes-prediction-model
```

## Deploy to Kubernetes

```
kubectl apply -f k8s-deploy.yaml
```

## Option to run in kind

### Create a cluster
```
kind create cluster --name mlops
```

### Port forward 

```
kubectl port-forward service/diabetes-api-service 1111:80 --address 0.0.0.0
```

🙌 Credits

Created by `ABHISHEK VEERAMALLA`

Subscribe for more DevOps + MLOps content on the YouTube Channel - `Abhishek.Veeramalla`

