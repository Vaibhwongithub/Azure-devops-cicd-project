# Azure DevOps CI/CD Pipeline Project-This project automates the entire software delivery lifecycle. When developers push code to GitHub, Azure DevOps pipelines automatically trigger the build process. The application is containerized using Docker, stored in Azure Container Registry, and deployed to AKS. Terraform provisions and manages the infrastructure. This ensures faster, reliable, and scalable deployments.

## Technologies
- Azure DevOps
- Docker
- Kubernetes
- Terraform
- GitHub

## Features
- CI/CD Pipeline
- Docker Containerization
- Kubernetes Deployment
- Infrastructure as Code

Project Architecture-->

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


## Prerequisites

- Azure Subscription
- Azure DevOps Account
- GitHub Account
- Docker Installed
- Terraform Installed
- kubectl Installed

---

CI/CD Workflow---->
Developer pushes code to GitHub
Azure DevOps triggers pipeline
Docker image gets built
Image pushed to Azure Container Registry
Terraform provisions infrastructure
Kubernetes deployment updated automatically



## Setup Instructions

### Clone Repository

```bash
git clone https://github.com/yourusername/Azure-devops-cicd-project.git
cd Azure-devops-cicd-project

Terraform Deployment-
cd terraform
terraform init
terraform apply -auto-approve

Build Docker Image-
cd app
docker build -t nodejs-app .

Push Image to ACR-
docker tag nodejs-app YOUR_ACR_NAME.azurecr.io/nodejs-app:latest
docker push YOUR_ACR_NAME.azurecr.io/nodejs-app:latest

Kubernetes Deployment-
kubectl apply -f kubernetes/




