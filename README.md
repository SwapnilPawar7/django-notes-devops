<div align="center">
  
# 🚀 Django Notes App — DevOps CI/CD Project
  
![GitHub Workflow Status](https://img.shields.io/badge/Building-Passing-brightgreen?style=for-the-badge)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker)
![AWS](https://img.shields.io/badge/AWS-EC2-FF9900?style=for-the-badge&logo=amazonaws)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-2088FF?style=for-the-badge&logo=githubactions)
  
[![Deployment Status](https://img.shields.io/badge/Deployment-Active-success?style=flat-square)](https://github.com/SwapnilPawar7/django-notes-devops)
[![Docker Pulls](https://img.shields.io/badge/Docker%20Pulls-Automated-blue?style=flat-square)](https://hub.docker.com/)
  
</div>

---

## 📌 Overview

This project demonstrates an **end-to-end DevOps pipeline** for deploying a Django-based application using modern containerization and CI/CD automation practices. Every code push automatically triggers a complete deployment cycle.


## ⚙️ Tech Stack

### DevOps & Infrastructure
- **Docker** - Containerization platform
- **GitHub Actions** - CI/CD automation
- **AWS EC2** - Cloud hosting

---

---

## Architecture (CI/CD + Infrastructure Combined)

        ┌──────────────────────────┐
        │        Developer         │
        │     (Local Machine)      │
        └────────────┬─────────────┘
                     ↓
        ┌──────────────────────────┐
        │         GitHub           │
        │   Source Code Repo       │
        └────────────┬─────────────┘
                     ↓
        ┌──────────────────────────┐
        │    GitHub Actions CI     │
        │  - Build Docker Image    │
        │  - Push to Registry      │
        └────────────┬─────────────┘
                     ↓
        ┌──────────────────────────┐
        │      Docker Hub          │
        │   Image Registry         │
        └────────────┬─────────────┘
                     ↓
        ┌──────────────────────────┐
        │      AWS EC2 Server      │
        │                          │
        │  ┌────────────────────┐  │
        │  │   Docker Engine    │  │
        │  │                    │  │
        │  │  ┌──────────────┐  │  │
        │  │  │ Django App   │  │  │
        │  │  │ (Gunicorn)   │  │  │
        │  │  └──────┬───────┘  │  │
        │  │         ↓          │  │
        │  │     Database       │  │
        │  │                    │  │
        │  └────────────────────┘  │
        │           ↑              │
        │        Nginx             │
        └──────────┬───────────────┘
                   ↓
             End Users Access App

## 🔄 CI/CD Pipeline Workflow

### Pipeline Stages

| Stage | Action | Description |
|-------|--------|-------------|
| **Stage 1** | 📝 Code Push | Developer pushes code to GitHub repository |
| **Stage 2** | 🔨 Build | GitHub Actions builds Docker image with dependencies |
| **Stage 3** | 📤 Push | Image is pushed to Docker Hub registry |
| **Stage 4** | 🚀 Deploy | EC2 instance pulls and runs the new container |


---

### Complete Workflow Example

```bash
# 1. Build the image
docker build -t django-notes-app:latest .

# 2. Run the container
docker run -d --name notes-app -p 8000:8000 django-notes-app:latest

# 3. Verify it's running
docker ps | grep notes-app

# 4. Check logs if needed
docker logs notes-app --tail 50

# 5. Stop and remove when done
docker stop notes-app
docker rm notes-app
```

###Access Your Application

```
# Development
http://localhost:8000

# Production
http://your-ec2-public-ip
```

### Setup Instructions

```
# Step 1: Clone the repository
git clone https://github.com/SwapnilPawar7/django-notes-devops.git

# Step 2: Navigate to project directory
cd django-notes-devops

# Step 3: Create virtual environment
python -m venv venv

# Step 4: Activate virtual environment
# On macOS/Linux:
source venv/bin/activate
# On Windows:
# venv\Scripts\activate

# Step 5: Install dependencies
pip install -r requirements.txt

# Step 6: Run database migrations
python manage.py migrate

# Step 7: Start development server
python manage.py runserver

# Step 8: Open browser to http://localhost:8000
```





