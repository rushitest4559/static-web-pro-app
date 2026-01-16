# Static Web Pro App

This repository contains a plain static website (**HTML, CSS, JS, images — no React/Angular**) along with a **production-grade CI/CD pipeline** to deploy the site across **multiple Azure environments**.

---

## 🚀 What This Project Does

- Hosts a static website on **Azure Storage Static Website**
- Deploys automatically to **DEV → STAGE → PROD**
- Uses **GitHub Actions + Azure OIDC** (no secrets, no passwords)
- Enforces **manual approval gates** between environments using **GitHub Environments**

---

## 🔄 CI/CD Pipeline Overview

### Trigger

- Push to `main` branch

### Flow

1. Deploy to **DEV**
2. Manual approval → Deploy to **STAGE**
3. Manual approval → Deploy to **PROD**
![Demo](./assets/cicd.mp4)

### Key Features

- Azure authentication via **OIDC**
- **Environment-specific** storage accounts
- Sequential promotion using `needs`
- Clean, simple deployment using  
  `az storage blob upload-batch`

---

## 🌐 Environments

| Environment | URL |
|------------|-----|
| **DEV** | https://rushistaticsitesadev.z13.web.core.windows.net |
| **STAGE** | https://rushistaticsitesastage.z13.web.core.windows.net |
| **PROD** | https://rushistaticsitesaprod.z13.web.core.windows.net |

---

## 🏗 Infrastructure

All Azure infrastructure for this project is provisioned using **Terraform**.

👉 **Infra repository:**  
https://github.com/rushitest4559/static-web-pro-infra

---

## 🛠 Tech Stack

- Static **HTML / CSS / JS**
- **GitHub Actions**
- **Azure Storage (Static Website)**
- **Azure OIDC Authentication**
- **Terraform** (for infra)

---

## 📌 Next Plans

- Add rollback mechanism in CI/CD
- Implement canary deployments
- Replace manual approvals with automated tests
- Add basic smoke & availability checks
