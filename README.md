# 🚀 CI/CD Pipeline for Django Application using Jenkins, Docker, AWS EC2 & Jenkins Shared Libraries

## 📌 Project Overview

This project demonstrates a fully automated CI/CD pipeline for a Django-based To-Do application using Jenkins, Docker, GitHub Webhooks, AWS EC2, and Jenkins Shared Libraries.

The pipeline follows a real-world DevOps production-style architecture where every code push to GitHub automatically triggers build, Docker image creation, push to Docker Hub, and deployment using Docker Compose.

---

## 🏗️ Architecture

        GitHub Repository
                ↓
        GitHub Webhook Trigger
                ↓
        Jenkins Master (AWS EC2)
                ↓
        Jenkins Agent / Worker Node (AWS EC2)
                ↓
        Jenkins Shared Library Loaded
                ↓
        Clone Source Code from GitHub
                ↓
        Build Docker Image (Django App)
                ↓
        Push Image to Docker Hub
                ↓
        Docker Compose Deployment
                ↓
        Nginx Reverse Proxy (Port 80)
                ↓
        Gunicorn + Django Application (Port 8000)
                ↓
        MySQL Database (Persistent Volume)

---

## ⚙️ Key Features

- Fully automated CI/CD pipeline
- Jenkins Master-Agent architecture
- Jenkins Shared Libraries (Reusable pipeline functions)
- GitHub Webhook integration
- Dockerized Django application
- Docker Hub image build & push automation
- Docker Compose multi-container deployment
- Nginx reverse proxy setup
- MySQL database with persistent storage
- Health checks for services
- Environment variable-based configuration

---

## 🛠️ Tech Stack

CI/CD & Automation:
- Jenkins
- GitHub Webhooks
- Jenkins Shared Libraries (Groovy)

Cloud Infrastructure:
- AWS EC2 (Master + Worker Node)

Containerization:
- Docker
- Docker Compose
- Docker Hub

Application Stack:
- Django (Python)
- Gunicorn (WSGI Server)
- MySQL (Database)
- Nginx (Reverse Proxy)

---

## 🔄 CI/CD Workflow

1. Code Push
Developer pushes code to GitHub repository.

2. Webhook Trigger
GitHub Webhook automatically triggers Jenkins pipeline.

3. Pipeline Execution
Jenkins Master assigns job to Worker Node.

        Shared Library loaded:
        @Library("Shared") _
        
        Functions:
        - hello()
        - clone(repo, branch)
        - push_to_dockerhub(image, tag, credentials)

4. Code Checkout
Worker node clones repository.

5. Docker Image Build & Push
Docker image is built and pushed to Docker Hub.

6. Deployment
docker compose down && docker compose up -d

7. Nginx Routing
Nginx forwards traffic to Django app via Gunicorn.

8. Database
MySQL runs with persistent storage.

---

## 🧩 Jenkins Shared Library

Reusable functions:
- clone()
- push_to_dockerhub()
- hello()

Benefits:
- Reusability
- Clean pipeline
- Scalability

---

## 🔐 Security Practices

- Jenkins credentials used
- No hardcoded secrets
- Environment variables (.env)
- Docker isolated networking

---

## 📈 Future Enhancements

- Kubernetes deployment
- AWS ECR instead of Docker Hub
- Terraform IaC
- SonarQube integration
- Monitoring with Prometheus & Grafana
- Logging with ELK stack

---

## 👨‍💻 Author

Adnan Shaikh  
DevOps Engineer | AWS | Jenkins | Docker | CI/CD

---

## ⭐ Summary

Automated CI/CD pipeline using Jenkins, Docker, AWS EC2, and Shared Libraries.
