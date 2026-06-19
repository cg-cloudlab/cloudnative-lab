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

```text
cloudnative-lab/
├── bootstrap/
│   └── kind-cluster.yaml
├── infrastructure/
│   ├── ingress-nginx/
│   ├── cert-manager/
│   ├── argocd/
│   └── harbor/
├── security/
│   ├── kyverno/
│   ├── trivy/
│   └── falco/
├── ai/
│   ├── ollama/
│   ├── open-webui/
│   └── rag/
└── apps/
