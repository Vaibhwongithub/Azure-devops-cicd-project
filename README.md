# Azure DevOps CI/CD Pipeline Project

## Overview

This project demonstrates a complete CI/CD pipeline implementation using:

- Azure DevOps
- Docker
- Kubernetes
- Terraform
- GitHub
- Azure Kubernetes Service (AKS)
- Azure Container Registry (ACR)

---

# Project Architecture

```text
Developer Pushes Code -> GitHub Repository
                                |
                                v
                     Azure DevOps Pipeline
                                |
            ------------------------------------
            |                |                 |
            v                v                 v
       Build App      Build Docker      Terraform Apply
                             Image             |
                               |               v
                               v         Create AKS + ACR
                        Push to ACR            |
                               |               v
                               --------> Kubernetes Deploy
```

---

# Folder Structure

```text
azure-devops-cicd-project/
│
├── app/
│   ├── index.js
│   ├── package.json
│   └── Dockerfile
│
├── kubernetes/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── namespace.yaml
│
├── terraform/
│   ├── main.tf
│   ├── provider.tf
│   ├── variables.tf
│   └── outputs.tf
│
├── scripts/
│   ├── build.sh
│   └── deploy.sh
│
├── azure-pipelines.yml
├── README.md
└── .gitignore
```

---

# Technologies Used

| Tool | Purpose |
|------|----------|
| Azure DevOps | CI/CD Pipeline |
| Docker | Containerization |
| Kubernetes | Container Orchestration |
| Terraform | Infrastructure as Code |
| GitHub | Version Control |
| AKS | Managed Kubernetes |
| ACR | Docker Image Registry |

---

# Features

- Automated CI/CD pipeline
- Docker containerization
- Kubernetes deployment
- Infrastructure provisioning using Terraform
- GitHub integration
- Automated deployments using Azure DevOps

---

# CI/CD Workflow

1. Developer pushes code to GitHub
2. Azure DevOps pipeline gets triggered
3. Application is built automatically
4. Docker image is created
5. Image is pushed to Azure Container Registry
6. Terraform provisions infrastructure
7. Kubernetes deployment gets updated

---

# Prerequisites

- Azure Subscription
- Azure DevOps Account
- GitHub Account
- Docker Installed
- Terraform Installed
- kubectl Installed

---

# Setup Instructions

## Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/azure-devops-cicd-project.git

cd azure-devops-cicd-project
```

---

## Terraform Deployment

```bash
cd terraform

terraform init

terraform apply -auto-approve
```

---

## Docker Build

```bash
cd app

docker build -t nodejs-app .
```

---

## Kubernetes Deployment

```bash
kubectl apply -f kubernetes/
```

---

# Azure DevOps Pipeline

The pipeline performs:

- Build
- Test
- Docker Image Creation
- Push to ACR
- Terraform Apply
- Kubernetes Deployment

---

# Verification Commands

## Check Pods

```bash
kubectl get pods -n devops-demo
```

## Check Services

```bash
kubectl get svc -n devops-demo
```

## Check Nodes

```bash
kubectl get nodes
```

---

# Sample Output

```text
Azure DevOps CI/CD Pipeline Working Successfully
```

---

# Future Enhancements

- Helm Charts
- Prometheus Monitoring
- Grafana Dashboards
- ArgoCD GitOps
- SonarQube Integration
- Trivy Security Scanning

---




git push -u origin main
```
