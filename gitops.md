# 🚀 GitOps Platform Architecture

<p align="center">

![Kubernetes](https://img.shields.io/badge/Kubernetes-K3s-326CE5?logo=kubernetes&logoColor=white)
![GitOps](https://img.shields.io/badge/GitOps-ArgoCD-EF7B4D?logo=argo&logoColor=white)
![CI/CD](https://img.shields.io/badge/CI/CD-GitHub%20Actions-2088FF?logo=githubactions&logoColor=white)
![Registry](https://img.shields.io/badge/Registry-Harbor-60B932)
![Monitoring](https://img.shields.io/badge/Monitoring-Prometheus-E6522C?logo=prometheus&logoColor=white)
![Dashboard](https://img.shields.io/badge/Dashboard-Grafana-F46800?logo=grafana&logoColor=white)

</p>

---

## 🏗️ Architecture

```mermaid
flowchart TD

    A[👨‍💻 Developers]
    B[📂 GitHub / Gitea]
    C[⚙️ GitHub Actions]
    D[📦 Harbor Registry]
    E[🚀 ArgoCD]
    F[☸️ K3s Cluster]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F

    subgraph K3s["☸️ K3s Cluster"]
        T[🌐 Traefik]
        CM[🔐 cert-manager]
        LH[💾 Longhorn]
        ESO[🔑 External Secrets Operator]
        INF[🛡️ Infisical]
        PRO[📈 Prometheus]
        GRA[📊 Grafana]
        LOK[📜 Loki]
        KYV[🛡️ Kyverno]
        TRI[🔍 Trivy]
        VEL[💾 Velero]
        APP[🚀 Applications]
    end

    F --> T
    F --> CM
    F --> LH
    F --> ESO
    F --> INF
    F --> PRO
    F --> GRA
    F --> LOK
    F --> KYV
    F --> TRI
    F --> VEL
    F --> APP
```

---

# 🔄 GitOps Workflow

```text
        👨‍💻 Developers
              │
              ▼
      📂 GitHub / Gitea
              │
              ▼
     ⚙️ GitHub Actions
              │
              ▼
      📦 Harbor Registry
              │
              ▼
         🚀 ArgoCD
              │
              ▼
         ☸️ K3s Cluster
              │
   ┌──────────┼──────────┐
   ▼          ▼          ▼
🌐 Traefik  🔐 cert-manager  💾 Longhorn
🔑 ESO      🛡️ Infisical
📈 Prometheus
📊 Grafana
📜 Loki
🛡️ Kyverno
🔍 Trivy
💾 Velero
🚀 Applications
```

---

# 📦 Platform Components

| Category | Components |
|----------|------------|
| **Source Control** | GitHub / Gitea |
| **CI/CD** | GitHub Actions |
| **Container Registry** | Harbor |
| **GitOps** | ArgoCD |
| **Kubernetes** | K3s |
| **Ingress** | Traefik |
| **TLS** | cert-manager |
| **Storage** | Longhorn |
| **Secrets** | External Secrets Operator, Infisical |
| **Monitoring** | Prometheus, Grafana |
| **Logging** | Loki |
| **Security** | Kyverno, Trivy |
| **Backup** | Velero |
| **Workloads** | Applications |

---

# ⚡ Deployment Flow

```text
Code
 │
 ▼
GitHub/Gitea
 │
 ▼
GitHub Actions
 │
 ▼
Build Docker Image
 │
 ▼
Push to Harbor
 │
 ▼
Update GitOps Repo
 │
 ▼
ArgoCD Sync
 │
 ▼
Deploy to K3s
 │
 ▼
Applications Running
```

---

## ✨ Features

- 🚀 Fully GitOps-driven deployment
- 🔄 Automated CI/CD pipeline
- 📦 Private image registry with Harbor
- ☸️ Lightweight Kubernetes using K3s
- 🔒 Centralized secrets management
- 📈 Monitoring & Alerting
- 📜 Centralized logging
- 🛡️ Policy enforcement & vulnerability scanning
- 💾 Automated backups with Velero
