# Cloud Native Lab

Cuneyt Gurses Personal cloud-native lab for Kubernetes, GitOps, Cloud Native Security, Private AI, RAG, and Air-Gapped/Sovereign AI scenarios.

## Current Components

- wsl
- calude
- wsc
- python
- kubernetes
- helm
- kind cluster
- Ingress NGINX
    - test nginx app
    - localhost ingress erişimi
- Metrics Server
- ArgoCD
- GitHub
- GitOps


## Target Lab Areas

- Kubernetes
- GitOps
- Cloud Native Security
- Harbor Registry
- Private AI
- RAG
- Air-gapped environments
- Sovereign AI Platform

## Repository Structure

cloudnative-lab/
│
├── README.md
│
├── bootstrap/
│   └── kind/
│       └── kind-cluster.yaml
│
├── infrastructure/
│   │
│   ├── argocd/
│   │   ├── root-app.yaml
│   │   └── apps/
│   │       ├── demo-nginx-app.yaml
│   │       ├── cert-manager-app.yaml
│   │       ├── harbor-app.yaml
│   │       ├── kyverno-app.yaml
│   │       ├── trivy-app.yaml
│   │       └── falco-app.yaml
│   │
│   ├── ingress-nginx/
│   ├── cert-manager/
│   └── harbor/
│
├── security/
│   ├── kyverno/
│   ├── trivy/
│   └── falco/
│
├── ai/
│   ├── ollama/
│   ├── open-webui/
│   └── rag/
│
└── apps/
    │
    ├── demo-nginx/
    │   ├── deployment.yaml
    │   ├── service.yaml
    │   ├── ingress.yaml
    │   └── kustomization.yaml
    │
    └── future-apps/
