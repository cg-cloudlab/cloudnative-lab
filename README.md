# Cloud Native Lab

Personal cloud-native lab for Kubernetes, GitOps, Cloud Native Security, Private AI, RAG, and Air-Gapped/Sovereign AI scenarios.

## Current Components

- WSL2
- Docker
- kind Kubernetes cluster
- Ingress NGINX
- Metrics Server
- ArgoCD

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
