# Azure Resource Insights Dashboard

## 📘 Project Name: Azure Resource Insights Dashboard

**Description:**  
A containerized web app (React frontend + FastAPI backend) that connects to your Azure account and displays all your resources, costs, and performance metrics in a clean dashboard view.

This project demonstrates your DevOps and cloud engineering skills: Azure API integration, Dockerization, secure credential handling, and full-stack architecture.

---

## 📌 Objectives

- 🔎 List all Azure resources (grouped by subscription, resource group, or type)
- 📊 Show cost breakdown by service, resource group, or tag
- 📈 Show performance metrics (e.g., CPU usage, disk IO) for VMs or App Services
- ✅ Containerized frontend & backend
- ☁️ Deployable to AKS or Azure App Service

---

## 📐 Architecture Diagram (Text-based)

```
          +------------------------+
          |      Frontend UI       |
          |  (React App in Docker) |
          +-----------+------------+
                      |
                      | REST API Calls
                      ↓
        +-------------+--------------+
        |         Backend API        |
        |   (FastAPI in Docker)      |
        |                            |
        | - Auth with Azure via SDK |
        | - Fetch cost/resource data|
        | - Serve API to frontend   |
        +-------------+--------------+
                      |
                      ↓
          +-----------+------------+
          |    Azure APIs (via SDK)|
          | - Resource Management  |
          | - Resource Graph       |
          | - Monitor Metrics      |
          | - Cost Mgmt & Billing  |
          +------------------------+

  [Optional]
  - Host in AKS or Azure App Service
  - Use Azure Key Vault for secrets
```

---

## 🗂️ Project Folder Structure

```
/azure-dashboard
  ├── frontend/               # React app
  │   ├── components/
  │   ├── App.jsx / .tsx
  │   ├── Dockerfile
  ├── backend/                # FastAPI backend
  │   ├── main.py
  │   ├── azure_client.py     # Handles Azure SDK calls
  │   ├── Dockerfile
  ├── docker-compose.yml
  ├── .env                    # Store local secrets (for dev)
  └── README.md
```

---

## ✅ Project Tasks (Milestone Checklist)

### 📦 Phase 1: Backend API

- [ ] Set up **FastAPI** project
- [ ] Create API routes:
  - `/resources`
  - `/costs`
  - `/metrics`
- [ ] Implement **Azure SDK auth** (client ID, tenant ID, secret)
- [ ] Query **Azure Resource Graph** for all resources
- [ ] Query **Cost Management API** for cost breakdown
- [ ] Query **Azure Monitor** for performance metrics
- [ ] Handle errors + logging

### 🎨 Phase 2: Frontend UI

- [ ] Create **React app** (Vite or CRA)
- [ ] Build dashboard layout (cards, tables, charts)
- [ ] Add pages:
  - Resource List
  - Cost Analytics
  - Performance Metrics
- [ ] Call backend API for data
- [ ] Add loading/error states

### 🐳 Phase 3: Docker + Local Dev

- [ ] Write **Dockerfiles** for frontend & backend
- [ ] Create **docker-compose.yml** for local testing
- [ ] Set up `.env` for secrets/configs
- [ ] Ensure app works with local Azure credentials

### ☁️ Phase 4: Cloud Deployment (Optional)

- [ ] Push images to **Azure Container Registry**
- [ ] Deploy to:
  - [ ] **Azure Kubernetes Service (AKS)** _OR_
  - [ ] **Azure App Service (Container)**
- [ ] Set up **Key Vault** or secret injection
- [ ] Set up basic CI/CD with GitHub Actions

---

## 🔐 Azure Setup Required

Before using the Azure APIs:
- [ ] Create **Azure AD App Registration**
- [ ] Assign **"Reader"** role on subscription/resource group
- [ ] Assign **"Cost Management Reader"** role
- [ ] Store **Client ID, Tenant ID, Secret** in local `.env` (or Key Vault)

---

## 🧠 Key Tools & Tech

| Layer      | Tech                     |
|------------|--------------------------|
| Frontend   | React, Chart.js / Recharts |
| Backend    | Python, FastAPI, Azure SDKs |
| Azure APIs | Resource Graph, Cost Management, Monitor |
| Auth       | Azure AD App Registration (Service Principal) |
| DevOps     | Docker, Docker Compose, GitHub Actions |
| Hosting    | AKS / App Service, ACR, Key Vault (optional) |

---

## 📎 Useful Azure SDKs for Python

```bash
pip install azure-identity azure-mgmt-resource azure-mgmt-monitor azure-mgmt-costmanagement
```
