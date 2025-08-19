# Django Notes App (Docker + MySQL + Kubernetes)

A Dockerized Django Notes application connected to a MySQL database, fully deployable on Kubernetes. Demonstrates containerization, secret management, REST API development, and Kubernetes deployment best practices.

---

## Technologies & Tools Used

- **Backend Framework:** Django 4.1.5  
- **Database:** MySQL 8  
- **API:** Django REST Framework  
- **Containerization:** Docker  
- **Orchestration:** Docker Compose (local), Kubernetes (production-like deployment)  
- **Secrets Management:** Kubernetes Secrets  
- **Persistent Storage:** Kubernetes Persistent Volumes (PVC)  
- **Web Server:** Gunicorn  
- **Frontend Integration:** Serve React build via Django templates (optional)  
- **Middleware:** CORS, Whitenoise for static file handling  
- **Networking:** Kubernetes Services, Port-forwarding for local testing  
- **Version Control & CI/CD (optional):** GitHub, Docker Hub  
- **Monitoring & Logs:** `kubectl logs`, container logs inspection  

---

## Features

- REST API endpoints for Notes CRUD operations  
- MySQL database for persistent storage  
- Fully containerized using Docker  
- Local development with Docker Compose  
- Kubernetes Deployment with:
  - Secrets for environment variables
  - Persistent Volumes for MySQL data
  - Init Containers to wait for MySQL readiness
- Port-forwarding to access the app locally
- Environment variables fully configurable
