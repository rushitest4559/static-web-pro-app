# Static Web Pro – Application CI/CD

This repository contains the **static website application** and its **production-style CI/CD pipeline** for Azure, implemented using **GitHub Actions**.

The pipeline deploys the application to **DEV → STAGE → PROD** with **manual approval gates** to demonstrate real-world release controls.

---

## 🚀 What This Repository Does

- Hosts static website source code
- Builds and deploys the app via **GitHub Actions**
- Deploys sequentially to:
  - DEV
  - STAGE
  - PROD
- Enforces **manual approvals** before higher environments
- No manual deployment via Azure Portal

---

## 🔄 CI/CD Pipeline Overview

### Trigger
- Push or merge to `main` branch

---

### Deployment Flow

1. **DEV Deployment**
   - Automatic
   - Used for early validation and testing

2. **STAGE Deployment**
   - Requires **manual approval**
   - Simulates pre-production validation

3. **PROD Deployment**
   - Requires **manual approval**
   - Represents controlled production release

> This mirrors real-world CI/CD practices where production deployments are never fully automatic.

---

## 🔐 Security Model

- No hardcoded secrets in repository
- Authentication handled via **OIDC**
- Access controlled using Azure Entra ID and RBAC
- Environment protection rules enforce approvals

---

## 🏗 Environment Separation

- DEV, STAGE, and PROD are isolated
- Independent deployment steps per environment
- Failures stop the pipeline from progressing further

---

## 🎥 Demo

A full CI/CD demo video is available here:  
🎥 Demo: https://youtu.be/5KblggFtBkI

---

## 🔗 Related Repository

Infrastructure (Terraform + GitOps):  
👉 https://github.com/rushitest4559/static-web-pro-infra

---

## 🛠 Tech Stack

- Static Web Technologies (HTML / CSS / JS)
- GitHub Actions
- Azure Static Web Apps / Storage (depending on setup)
- Azure Entra ID
- OIDC Authentication

---

## 🧠 Key Takeaway

This project demonstrates **safe, production-style application delivery**:
- Automated deployments
- Manual approval gates
- Clear separation between application and infrastructure
- Git as the single source of truth
