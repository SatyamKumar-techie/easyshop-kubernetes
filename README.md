# 🚀 EasyShop Kubernetes Deployment

A production-style Kubernetes deployment of EasyShop application with MongoDB, Redis, HPA, Ingress, TLS and ArgoCD integration.

---

## 📦 Tech Stack

- Kubernetes
- MongoDB (StatefulSet)
- Redis
- Deployment & Services
- HPA (Horizontal Pod Autoscaler)
- Ingress
- TLS (Self Signed Issuer)
- ArgoCD
- Kustomize

---

## 🏗 Architecture Components

- Namespace
- ConfigMap & Secrets
- Persistent Volume & PVC
- MongoDB StatefulSet
- EasyShop Deployment (2 replicas)
- HPA (2-5 replicas)
- Migration Job
- Ingress Controller
- Redis Deployment
- ArgoCD Application

---

## 🚀 Deployment

```bash
kubectl apply -k .
