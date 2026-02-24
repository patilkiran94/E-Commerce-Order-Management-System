# 🚀 Order Management System – DevOps Project

A complete **end-to-end DevOps project** demonstrating how to build, containerize, deploy, monitor, and automate a Spring Boot microservice using modern DevOps tools on AWS.

This project follows **real industry practices** including CI/CD, Kubernetes, monitoring, and Infrastructure as Code.

---

## 🧩 Project Overview

This project deploys a **Spring Boot Order Management REST API** on **AWS EKS** using Docker and Kubernetes, with CI/CD automation via Jenkins and infrastructure provisioning using Terraform.

---

## 🏗️ Architecture Summary

- Application: Spring Boot (REST API)
- Containerization: Docker
- Orchestration: Kubernetes (AWS EKS)
- CI/CD: Jenkins
- Monitoring: Prometheus & Grafana
- Infrastructure as Code: Terraform
- Cloud Provider: AWS
- Source Control: GitHub

---

## 🛠️ Tech Stack

| Category | Tools |
|-------|------|
| Backend | Java, Spring Boot |
| Build Tool | Maven |
| Container | Docker |
| Orchestration | Kubernetes (EKS) |
| CI/CD | Jenkins |
| Monitoring | Prometheus, Grafana |
| IaC | Terraform |
| Cloud | AWS |
| SCM | GitHub |

---

## 📁 Project Structure
order-management-devops/
│
├── app/
│ ├── src/main/java/com/example/order
│ ├── src/main/resources/application.yml
│ └── pom.xml
│
├── docker/
│ └── Dockerfile
│
├── k8s/
│ ├── deployment.yml
│ ├── service.yml
│ ├── prometheus.yml
│ └── grafana.yml
│
├── terraform/
│ ├── provider.tf
│ ├── variables.tf
│ ├── vpc.tf
│ ├── eks.tf
│ └── outputs.tf
│
├── Jenkinsfile
└── README.md


---

## ⚙️ CI/CD Pipeline (Jenkins)

1. Pull code from GitHub
2. Build Spring Boot app using Maven
3. Build Docker image
4. Push image to Docker Hub
5. Deploy application to AWS EKS

---

## ☁️ Infrastructure (Terraform)

Terraform provisions:
- VPC with public & private subnets
- Internet Gateway & NAT Gateway
- EKS Cluster
- Managed Node Groups

---

## 📦 Kubernetes Deployment

- Application deployed using Kubernetes Deployment
- Exposed via NodePort Service
- Auto-scaling ready
- Prometheus scrapes application metrics
- Grafana visualizes metrics

---

## 📊 Monitoring

- Prometheus collects metrics from Spring Boot actuator
- Grafana dashboards visualize:
  - Pod health
  - API request count
  - JVM memory & CPU usage

---

## 🚀 How to Deploy

### 1️⃣ Provision Infrastructure
```bash
cd terraform
terraform init
terraform apply

### 2️⃣ Configure kubectl
aws eks update-kubeconfig --region ap-south-1 --name order-eks-terraform

### 3️⃣ Deploy Application
kubectl apply -f k8s/

### 4️⃣ Access Application
http://<NODE_PUBLIC_IP>:30007/orders
