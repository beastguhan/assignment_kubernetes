Flask Kubernetes App
Overview
This is a simple Python Flask app deployed on a local Kubernetes cluster using Minikube.

Setup Instructions

1️⃣ Start Minikube

minikube start
minikube docker-env | Invoke-Expression

2️⃣ Build Docker Image
docker build -t flask-k8s-demo:latest .

3️⃣ Deploy to Kubernetes
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl rollout restart deployment flask-deployment
kubectl get pods -w

4️⃣ Access the App 
minikube service flask-service
