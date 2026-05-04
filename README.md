# 🚀 React Application with CI/CD & Kubernetes Deployment

## 📌 Overview

This project is a React-based web application built and deployed using modern DevOps practices. It demonstrates an end-to-end workflow including containerization, CI/CD automation, and Kubernetes orchestration.

The objective of this project is to showcase practical implementation of:

* Continuous Integration & Continuous Deployment (CI/CD)
* Containerization using Docker
* Kubernetes-based scalable deployment

---

## 🛠️ Tech Stack

* **Frontend:** React.js
* **Version Control:** Git & GitHub
* **Containerization:** Docker
* **CI/CD Tool:** Jenkins
* **Orchestration:** Kubernetes
* **Cloud (Optional):** AWS (EC2 / EKS)

---

## ⚙️ Features

* Modern React UI
* Dockerized application for consistent deployment
* Automated CI/CD pipeline
* Kubernetes Deployment for scaling
* Kubernetes Service for exposing the application

---

## 🏗️ Architecture

User → Browser → React App → Docker Container → Kubernetes Cluster

CI/CD Pipeline:
GitHub → Jenkins → Build → Docker Image → Deploy to Kubernetes

---

## 🚀 Getting Started

### 📌 Prerequisites

Make sure you have installed:

* Node.js
* Docker
* Kubernetes (Minikube or any cluster)
* kubectl

---

### 🔧 Local Setup

```bash
# Clone repository
git clone https://github.com/santhosh9880/react-app.git

# Navigate to project
cd react-app

# Install dependencies
npm install

# Start application
npm start
```

---

## 🐳 Docker Setup

```bash
# Build Docker image
docker build -t react-app .

# Run container
docker run -d -p 3000:3000 react-app
```

---

## ☸️ Kubernetes Deployment

### 📄 Deployment Configuration

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: react-app-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: react-app
  template:
    metadata:
      labels:
        app: react-app
    spec:
      containers:
      - name: react-app
        image: react-app:latest
        ports:
        - containerPort: 3000
```

---

### 🌐 Service Configuration

```yaml
apiVersion: v1
kind: Service
metadata:
  name: react-app-service
spec:
  type: NodePort
  selector:
    app: react-app
  ports:
    - port: 80
      targetPort: 3000
      nodePort: 30007
```

---

### ▶️ Deploy to Kubernetes

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

---

## 🔁 CI/CD Pipeline (Jenkins)

* Code is pushed to GitHub repository
* Jenkins pipeline is triggered automatically
* Application is built and Docker image is created
* Deployment is updated in Kubernetes cluster

---

## 📂 Project Structure

```
react-app/
│── src/
│── public/
│── Dockerfile
│── Jenkinsfile
│── deployment.yaml
│── service.yaml
│── package.json
│── README.md
```

---

## 📸 Screenshots

*Add application screenshots here*

---

## 📌 Future Enhancements

* Implement Ingress Controller
* Use Helm Charts
* Add auto-scaling (HPA)
* Integrate monitoring (Prometheus & Grafana)
* Infrastructure provisioning using Terraform

---

## 👨‍💻 Author

**Santhosh**
GitHub: https://github.com/santhosh9880

---

## ⭐ Summary

This project demonstrates a real-world DevOps workflow by integrating development, automation, and deployment using modern tools and technologies.
