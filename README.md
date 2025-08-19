Django Notes App (Dockerized + Kubernetes)

This project is a Django-based Notes application with a MySQL database, fully containerized using Docker and deployed on Kubernetes. It demonstrates modern DevOps practices including Docker Compose orchestration, secret management, and Kubernetes deployment.

Features

Django backend with REST API endpoints

MySQL database for persistent storage

Fully containerized using Docker

Docker Compose for local development

Kubernetes Deployment with ConfigMaps, Secrets, Persistent Volumes, and Init Containers

Port-forwarding for local access during development

Getting Started
1. Clone the Repository
git clone <your-repo-url>
cd django-notes-app

2. Docker Compose Setup (Local Development)

Build and start containers:

docker-compose up --build


Services included:

notes-app (Django)

mysql (Database)

Access the app at http://localhost:8000

3. Push Docker Image to Docker Hub
docker build -t <your-dockerhub-username>/django-notes-app:latest .
docker push <your-dockerhub-username>/django-notes-app:latest

4. Kubernetes Deployment (Production/Cluster)

Namespace, Secrets, PVC, and Deployments configured

Apply manifests:

kubectl apply -f mysql-secret.yml
kubectl apply -f mysql-deployment.yml
kubectl apply -f notes-app-deployment.yml


Port-forward for local testing:

kubectl port-forward -n notes-app deployment/notes-app-deployment 8000:8000

5. Verify Pods and Logs
kubectl get pods -n notes-app
kubectl logs -n notes-app <pod-name> -c notes-app-container

6. Environment Variables

Database Config (Secret):

DB_NAME=test_db
DB_USER=root
DB_PASSWORD=root
DB_HOST=mysql
DB_PORT=3306


Django Config:

DJANGO_SECRET_KEY=abcd1234
DJANGO_ALLOWED_HOSTS=*

7. Key Highlights (Resume-ready)

Containerized Django + MySQL application

Configured Docker Compose for local orchestration

Deployed on Kubernetes with Secrets and Persistent Volumes

Implemented Init Container to wait for MySQL before Django migration

Hands-on experience with kubectl, port-forwarding, and deployment management