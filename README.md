# Cloud Native Platform Lab

Personal cloud-native lab focused on:

- Kubernetes
- GitOps
- Cloud Native Security
- Harbor Registry
- Private AI
- Retrieval-Augmented Generation (RAG)
- Air-Gapped Deployments
- Sovereign Cloud Scenarios

---

## Current Achievement

GitOps-managed application deployed from a private Harbor registry with TLS-enabled ingress on a local Kubernetes platform.

Current application image:

```text
harbor.local:80/library/nginx:1.29
```

---

## Current Status

### Platform Components

- Kubernetes v1.34 (kind)
- NGINX Ingress Controller
- Metrics Server
- Argo CD
- GitOps (App of Apps Pattern)
- Cert Manager
- Self-Signed ClusterIssuer
- Harbor Registry
- Harbor Trivy Scanner
- TLS-enabled Demo Application

---

## Repository Structure

```text
cloudnative-lab
├── README.md
│
├── ai
│   ├── ollama
│   ├── open-webui
│   └── rag
│
├── apps
│   └── demo-nginx
│       ├── deployment.yaml
│       ├── service.yaml
│       ├── ingress.yaml
│       └── kustomization.yaml
│
├── bootstrap
│   └── kind-cluster.yaml
│
├── infrastructure
│   ├── argocd
│   │   ├── root-app.yaml
│   │   └── apps
│   │       ├── demo-nginx-app.yaml
│   │       ├── cert-manager-app.yaml
│   │       ├── cert-manager-config-app.yaml
│   │       └── harbor-app.yaml
│   │
│   ├── cert-manager
│   │   ├── selfsigned-clusterissuer.yaml
│   │   ├── demo-nginx-certificate.yaml
│   │   └── kustomization.yaml
│   │
│   ├── harbor
│   └── ingress-nginx
│
└── security
    ├── falco
    ├── kyverno
    └── trivy
```

---

## GitOps Architecture

```text
GitHub Repository
        │
        ▼
ArgoCD Root Application
(platform-root)
        │
        ▼
Child Applications
        │
        ▼
Infrastructure Components
        │
        ▼
Application Deployments
```

---

## Certificate Flow

```text
cert-manager
      │
      ▼
ClusterIssuer
      │
      ▼
Certificate
      │
      ▼
TLS Secret
      │
      ▼
Ingress
      │
      ▼
HTTPS Service
```

---

## Registry Flow

```text
Docker Hub
      │
      ▼
Harbor Registry
      │
      ▼
Kubernetes Image Pull
      │
      ▼
Application Deployment
```

---

## Current Demo Application

Deployment:

```text
demo-nginx
```

Image:

```text
harbor.local:80/library/nginx:1.29
```

Ingress:

```text
https://demo.local
```

---

## Validation Commands

### Argo CD

```bash
kubectl get applications -n argocd
```

### Certificates

```bash
kubectl get certificate
kubectl get clusterissuer
kubectl get secret
```

### Harbor

```bash
kubectl get pods -n harbor
```

### Demo Application

```bash
kubectl get deployment demo-nginx
kubectl get pods
kubectl get ingress
```

### HTTPS Validation

```bash
curl -k -H "Host: demo.local" https://localhost
```

---

## Completed Milestones

### Platform

- Kubernetes Cluster
- NGINX Ingress
- Metrics Server

### GitOps

- Argo CD
- App of Apps Pattern

### Security

- Cert Manager
- Self-Signed ClusterIssuer
- TLS Certificates

### Registry

- Harbor Registry
- Harbor Image Push
- Harbor Image Pull

### Applications

- GitOps Deployment
- Harbor-based Deployment
- HTTPS-enabled Application

---

## Next Steps

### Security

- Harbor Vulnerability Scanning (Trivy)
- Image Signing (Cosign)
- Kyverno Policies
- Falco Runtime Security

### AI Platform

- Ollama
- Open WebUI
- Private RAG Platform

### Enterprise Scenarios

- Air-Gapped Deployment
- Defense Community Cloud Blueprint
- Sovereign Cloud Reference Architecture

---

## Technology Stack

| Category | Technology |
|-----------|------------|
| Container Runtime | Docker |
| Kubernetes | kind |
| Ingress | NGINX Ingress Controller |
| GitOps | Argo CD |
| Certificate Management | cert-manager |
| Registry | Harbor |
| Vulnerability Scanning | Trivy |
| Policy Engine | Kyverno |
| Runtime Security | Falco |
| AI Platform | Ollama / Open WebUI |
| Git Repository | GitHub |

---

## Author

**Cuneyt Gurses**

Lead Cloud Architect

Cloud Architecture • Kubernetes • GitOps • Cloud Native Security • Sovereign Cloud • Private AI
