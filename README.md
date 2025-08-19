# Django Notes App with Docker, MySQL & Kubernetes

A **Dockerized Django Notes application** connected to a **MySQL database**, fully deployable on **Kubernetes**. This project demonstrates modern DevOps practices including containerization, environment management, and scalable deployments.

---

## **Overview**

This project is a simple **Notes application** built with Django and Django REST Framework. Users can create, update, and delete notes via API endpoints. The app uses **MySQL** as the backend database and can be deployed locally via Docker or scaled on Kubernetes.

---

## **Tech Stack & DevOps Tools Used**

| Technology | Purpose |
|------------|---------|
| Django 4.1.5 | Web framework & REST API |
| Django REST Framework | API endpoints |
| MySQL 8 | Relational database |
| Docker | Containerization of app and database |
| Docker Compose | Local multi-container orchestration |
| Docker Hub | Image repository for pushing/pulling images |
| Kubernetes | Production-grade orchestration & scaling |
| Kubernetes Secrets & PVC | Secure environment variable management & persistent storage |
| Whitenoise | Serving static files in production |

---

## **Project Workflow / Steps**

1. **Set up Django App**
   - Create Django project & API app
   - Configure MySQL database connection using environment variables
   - Create models, migrations, and REST API endpoints

2. **Dockerize the App**
   - Write `Dockerfile` for Django app
   - Build Docker image locally
   - Run container locally
   - Test app functionality

3. **Docker Compose for Local Multi-Container Setup**
   - Configure `docker-compose.yml` with Django & MySQL
   - Start & stop services with Docker Compose
   - View logs for debugging

4. **Push Docker Image to Docker Hub**
   - Push built image to Docker Hub
   - Pull image from Docker Hub for deployment

5. **Deploy on Kubernetes**
   - Create namespace
   - Create MySQL Secret & PVC for persistent storage
   - Apply MySQL & Django deployments
   - Verify pods and logs
   - Port-forward for local access

6. **Scaling the App**
   - Scale deployment using `kubectl scale` for multiple replicas

---

## **Key Commands Used**

### Docker
```bash
docker build -t abd126/django-notes-app:latest .
docker run -it -p 8000:8000 --env-file .env abd126/django-notes-app:latest
docker ps
docker stop <container-id>
docker rm <container-id>
docker push abd126/django-notes-app:latest
