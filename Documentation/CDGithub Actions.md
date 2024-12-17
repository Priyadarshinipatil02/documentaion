# Project Documentation: AWS Infrastructure & GitHub Actions CI/CD Pipeline

This document provides an in-depth understanding of the AWS infrastructure and GitHub Actions CI/CD pipeline utilized in this project. It outlines architecture components, deployment pipelines, and maintenance guidelines.

---

## ☁️ AWS Infrastructure

### AWS Services Overview

The infrastructure utilizes AWS services to host application components, including the backend, frontend, and Kubernetes orchestration.

**Key AWS Services:**
- **Amazon Elastic Container Registry (ECR):** Container registry for Docker images.
- **Amazon Elastic Kubernetes Service (EKS):** Managed Kubernetes cluster for orchestration.
- **AWS IAM:** Identity and access management for controlling access to AWS services.
- **Amazon S3:** Used for storing static assets or backups.
- **AWS CloudWatch:** Monitoring and logging for all AWS infrastructure activities.
- **Amazon Route 53:** DNS routing for application endpoints.

---

### AWS Architecture Diagram

A high-level architecture diagram includes the following AWS components:

- **Frontend & Backend Deployment on AWS EKS**
  - **Containerized with Docker**
  - **Deployed using Kubernetes (EKS cluster)**
  
- **Docker Images**
  - Built in CI/CD pipelines using GitHub Actions.
  - Pushed to AWS ECR.
  
- **IAM Policies & Roles**
  - Ensure appropriate permissions for AWS ECR, EKS, and related services.
  
- **CloudWatch Logs**
  - Application logs streamed to CloudWatch for monitoring.

---

## ⚙️ GitHub Actions CI/CD Pipeline

### Pipeline Workflow Overview

The CI/CD pipeline automates build, testing, Docker image creation, deployment to AWS ECR, and Kubernetes updates. The pipeline consists of the following stages:

1. **Code Checkout:** Clone the repository.
2. **Environment Preparation:** Set up Node.js, Java, Maven, and other dependencies.
3. **Build & Scan:** Run code scans and perform dependency checks.
4. **Docker Image Build & Push:** Build frontend/backend Docker images and push to AWS ECR.
5. **Kubernetes Manifest Update:** Update Helm chart with the latest Docker image versions.
6. **Deployment:** Apply changes to the EKS cluster.

---

### Workflow Stages

1. **OWASP Scan and Dependencies Installation**
   - Configure dependencies (Node.js, Java, Maven).
   - Perform security scanning of dependencies using OWASP scanning tools.

2. **Docker Build**
   - Build and tag frontend and backend Docker images.

3. **Push Docker Images to AWS ECR**
   - Authenticate with AWS ECR.
   - Push frontend and backend Docker images to ECR.

4. **Update Helm Charts**
   - Dynamically replace Docker image tags in the `values-dev.yaml` manifest.
   - Push the updated Helm manifests back to the repository.

5. **Deployment to AWS EKS**
   - Use Helm to apply changes to the EKS cluster and deploy new versions of the frontend and backend.

---

## 🛠️ Setup Instructions

### AWS Setup

#### AWS Account Configuration
- Set up AWS credentials.
- Create necessary IAM roles for CI/CD pipeline functionality.

#### IAM Roles & Policies
- Create an IAM role with the following permissions:
  - `AmazonECRFullAccess`
  - `AmazonEKSClusterPolicy`

#### Setup EKS Cluster
Provision EKS clusters using the AWS Console, Terraform, or AWS CLI.

**Example Command:**
```bash
aws eks create-cluster \
  --name your-cluster-name \
  --role-arn arn:aws:iam::123456789012:role/eks-role \
  --resources-vpc-config subnetIds=subnet-0abcde1234567890
  ```

---

# GitHub Actions Workflow Configuration

## Repository Secrets

Add necessary AWS secrets to GitHub. Navigate to:

**Settings > Secrets and Variables > Actions**

Add the following secrets:
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION`
- `PAT` (Personal Access Token for repo access)

---

## Configure Self-Hosted Runners

If required, set up self-hosted runners on EC2 instances or private servers for the pipeline.

---

## 🔑 Access & Permissions

### GitHub Actions Permissions

Ensure GitHub Actions workflows have read/write permissions to:
- **AWS ECR**
- **AWS EKS**
- **Kubernetes manifests**

