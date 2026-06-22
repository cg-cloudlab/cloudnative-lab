# Cloud Native Lab

Cuneyt Gurses Personal cloud-native lab for Kubernetes, GitOps, Cloud Native Security, Private AI, RAG, and Air-Gapped/Sovereign AI scenarios.

Current Achievement: GitOps-managed application deployed from a private Harbor registry with TLS-enabled ingress on a local Kubernetes platform

Cloud Native Platform Lab
Current Status
Platform Components
Kubernetes v1.34 (kind)
Ingress NGINX
Metrics Server
Argo CD
GitOps (App of Apps Pattern)
Cert Manager
Self-Signed ClusterIssuer
Harbor Registry
Harbor Trivy Scanner
TLS Enabled Demo Application
Repository Structure
cloudnative-lab
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
GitOps Architecture

GitHub Repository
↓
ArgoCD Root Application
(platform-root)
↓
Child Applications
↓
Infrastructure Components
↓
Application Deployments

Certificate Flow

cert-manager
↓
ClusterIssuer
↓
Certificate
↓
TLS Secret
↓
Ingress
↓
HTTPS Service

Registry Flow

Docker Hub
↓
Harbor Registry
↓
Kubernetes Image Pull
↓
Application Deployment

Current demo application image:

harbor.local:80/library/nginx:1.29

Validation Commands

Check Applications

kubectl get applications -n argocd

Check Certificates

kubectl get certificate
kubectl get clusterissuer

Check Harbor

kubectl get pods -n harbor

Check Demo Application

kubectl get deployment demo-nginx
kubectl get pods

Test HTTPS

curl -k -H "Host: demo.local" https://localhost

Completed Milestones

✓ Kubernetes Cluster

✓ Ingress NGINX

✓ Metrics Server

✓ ArgoCD

✓ App of Apps Pattern

✓ Cert Manager

✓ TLS Certificates

✓ Harbor Registry

✓ Harbor Image Push

✓ Harbor Image Pull

✓ GitOps Deployment from Harbor Registry

Next Steps
Harbor Vulnerability Scanning (Trivy)
Image Signing
Kyverno Policies
Falco Runtime Security
Open WebUI
Ollama
Private RAG Platform
Air-Gapped Deployment Scenario
Defense Community Cloud Blueprint
Sovereign Cloud Reference Architecture
