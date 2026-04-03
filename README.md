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

### ✨ Key Highlights

| Feature | Description |
|---------|-------------|
| ✅ **Zero-downtime deployments** | Seamless updates without service interruption |
| ✅ **Automated testing** | Continuous integration with every commit |
| ✅ **Production-ready** | Optimized for real-world deployment |
| ✅ **Scalable architecture** | Designed for future growth |

---

## 🏗️ Architecture

Developer (Git Push)

        ↓
        
GitHub Repository

        ↓
        
GitHub Actions (CI/CD)

        ↓
        
Build Docker Image

        ↓
        
Push to Docker Hub

        ↓
        
SSH into EC2

        ↓
        
Pull Latest Image

        ↓
        
Run Container

        ↓
        
User Access via Public IP


### Component Breakdown

| Component | Role | Technology |
|-----------|------|------------|
| **Version Control** | Code repository | GitHub |
| **CI/CD Pipeline** | Automation | GitHub Actions |
| **Container Registry** | Image storage | Docker Hub |
| **Compute Service** | Hosting platform | AWS EC2 |
| **Runtime** | Application execution | Docker Container |

---

## ⚙️ Tech Stack

### Backend & Server
- **Django** - Python web framework for backend logic
- **Gunicorn** - WSGI HTTP server for Python
- **Nginx** - Reverse proxy and load balancer

### DevOps & Infrastructure
- **Docker** - Containerization platform
- **GitHub Actions** - CI/CD automation
- **AWS EC2** - Cloud hosting

### Tools & Registries
- **Docker Hub** - Container image registry
- **Git** - Version control system

---

## 🔄 CI/CD Pipeline Workflow

### Pipeline Stages

┌─────────────────────────────────────────────────────────────────────┐
│ CI/CD PIPELINE FLOW │
├──────────────┬──────────────────┬──────────────────┬────────────────┤
│ Stage 1 │ Stage 2 │ Stage 3 │ Stage 4 │
├──────────────┼──────────────────┼──────────────────┼────────────────┤
│ 📝 Code │ 🔨 Build │ 📤 Push │ 🚀 Deploy │
│ Push to │ Docker Image │ to Docker │ to EC2 │
│ GitHub │ with Dependencies│ Hub Registry │ Instance │
└──────────────┴──────────────────┴──────────────────┴────────────────┘


### Detailed Steps

| Step | Action | Status Indicator |
|------|--------|------------------|
| 1 | Code pushed to GitHub | 🟢 Triggered |
| 2 | GitHub Actions workflow starts | 🟡 Running |
| 3 | Docker image built with dependencies | 🟡 Building |
| 4 | Image pushed to Docker Hub | 🟡 Pushing |
| 5 | SSH connection to EC2 established | 🟡 Connecting |
| 6 | Latest image pulled from registry | 🟡 Pulling |
| 7 | Container restarted with new image | 🟡 Deploying |
| 8 | Health check verification | 🟢 Complete |

---

## 🐳 Docker Usage

### Basic Commands

| Command | Purpose |
|---------|---------|
| `docker build -t django-notes-app .` | Build Docker image |
| `docker run -d -p 8000:8000 django-notes-app` | Run container in background |
| `docker ps` | List running containers |
| `docker logs django-notes-app` | View container logs |
| `docker stop django-notes-app` | Stop running container |
| `docker rm django-notes-app` | Remove container |

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

### 📊 Project Dashboard
Current Status
Metric	Status	Details
CI/CD Pipeline	🟢 Operational	All checks passing
Deployment	🟢 Active	Running on EC2
Documentation	🟢 Complete	README + Wiki
Test Coverage	🟡 Partial	Unit tests in progress
Monitoring	🔴 Not started	Planned for Phase 3



