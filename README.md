# 🚀 Automated Portfolio Deployment on AWS Fargate  
A fully automated, production-grade deployment pipeline for my personal portfolio website, using Docker containers, Terraform-managed AWS infrastructure, and a complete CI/CD flow powered by GitHub Actions.  
The system runs on **serverless AWS ECS Fargate**, ensuring high availability, scalability, and zero server management.

---

## ✨ Features

- **Automated CI/CD:** Every push to GitHub triggers a full build, test, image push, and deployment to AWS.  
- **Containerized Deployment:** The portfolio is packaged into a Docker image for consistent runtime behavior across environments.  
- **Scalable Serverless Hosting:** Runs on AWS Fargate, eliminating the need to manage EC2 servers.  
- **Load Balanced:** Traffic is routed through an Application Load Balancer (ALB) for availability and failover.  
- **Cloud-Native Architecture:** Fully managed using Terraform for reproducible, version-controlled infrastructure.  
- **Secure Deployment:** IAM roles, OIDC GitHub authentication, HTTPS ALB, and isolated VPC networking.

---

## 🏗 Architecture Overview

### **Frontend**
- Built using **HTML, CSS, and JavaScript** (static portfolio).  
- Dockerized for consistent production builds.

### **Backend / Deployment Engine**
- **AWS ECS Fargate** running the portfolio container.  
- **Amazon ECR** stores all Docker images.  
- **Application Load Balancer (ALB)** distributes traffic to Fargate tasks.  
- **Terraform** provisions VPC, ECS cluster, Fargate services, ALB, IAM, and networking components.

### **CI/CD Pipeline**
- **GitHub Actions** automates:  
  - Docker build  
  - Push to ECR  
  - Terraform apply  
  - Rolling deployment to Fargate  

---

## 🧰 Tech Stack

| Layer | Technologies |
|-------|--------------|
| **Frontend** | HTML, CSS, JavaScript |
| **Containerization** | Docker |
| **Infrastructure** | Terraform, AWS VPC, ECS, ALB |
| **Orchestration** | AWS ECS Fargate |
| **Registry** | Amazon ECR |
| **CI/CD** | GitHub Actions |
| **Version Control** | Git & GitHub |

---

## ⚙️ Deployment Summary

### **1. CI/CD Pipeline Steps**
- Push code to GitHub.  
- GitHub Actions runs:  
  - `docker build`  
  - `docker push` to ECR  
  - Terraform commands to update infrastructure  
  - ECS Fargate deployment refresh  

### **2. Infrastructure Setup via Terraform**
- Create VPC with public and private subnets.  
- Provision ECS Cluster and Fargate Service.  
- Configure ALB (HTTPS supported).  
- Attach IAM roles for ECS & GitHub OIDC.  
- Create and manage Amazon ECR repository.

### **3. Application Deployment**
- ECS Fargate pulls the latest image from ECR.  
- ALB routes HTTP traffic to running tasks.  
- Health checks ensure zero downtime.

---

## 🔐 Security Highlights

- **HTTPS-ready architecture** via ALB with TLS support (ACM certificates can be added).  
- **IAM least-privilege roles** for ECS tasks and GitHub deployments.  
- **Private subnets** keep Fargate tasks isolated from the public internet.  
- **Security Groups** restrict inbound/outbound access.  
- **OIDC authentication** for GitHub Actions (avoids storing AWS keys).  

---

## 🌍 Live Demo  
🔗 **Portfolio Website:** Mohammed Hasham | https://share.google/6C4hZIxfglEWOpigS  

---

## 📁 Repository  
🔗 **GitHub Repo:** https://github.com/Hasham-03/portfolio-fargate  

---

## 👤 Author  
**Mohammed Hasham**   
🔗 GitHub Profile: https://github.com/Hasham-03  
