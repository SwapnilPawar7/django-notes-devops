<div align="center">
  
  # 🚀 Django Notes App — DevOps CI/CD Project
  
  ![GitHub Workflow Status](https://img.shields.io/badge/Building-Passing-brightgreen)
  ![Docker](https://img.shields.io/badge/Docker-Containerized-blue)
  ![AWS](https://img.shields.io/badge/AWS-EC2-orange)
  ![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-purple)
  ![Django](https://img.shields.io/badge/Django-4.2-darkgreen)
  
  <p align="center">
    <strong>Production-ready DevOps pipeline with automated deployment</strong>
  </p>
  
  [![Deployment Status](https://img.shields.io/badge/Deployment-Active-success)](https://github.com/SwapnilPawar7/django-notes-devops)
  [![Docker Pulls](https://img.shields.io/badge/Docker%20Pulls-Automated-blue)](https://hub.docker.com/)
  [![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)
  
</div>

---

## 📌 Overview

This project demonstrates an **end-to-end DevOps pipeline** for deploying a Django-based application using modern containerization and CI/CD automation practices. Every code push automatically triggers a complete deployment cycle.

### ✨ Key Highlights

- ✅ **Zero-downtime deployments** with container orchestration
- ✅ **Automated testing** and image building
- ✅ **Production-ready** configuration
- ✅ **Scalable architecture** for future growth

---

## 🏗️ Architecture

<div align="center">
  
```mermaid
graph LR
    A[GitHub Code] --> B[GitHub Actions]
    B --> C[Docker Build]
    C --> D[Docker Hub]
    D --> E[SSH to EC2]
    E --> F[Pull Image]
    F --> G[Run Container]
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#bbf,stroke:#333,stroke-width:2px
    style C fill:#6f9,stroke:#333,stroke-width:2px
    style D fill:#f96,stroke:#333,stroke-width:2px
    style E fill:#69f,stroke:#333,stroke-width:2px
    style F fill:#9f6,stroke:#333,stroke-width:2px
    style G fill:#ff9,stroke:#333,stroke-width:2px
