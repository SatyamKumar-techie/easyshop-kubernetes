## 🚀 Project Overview

This repository contains a production-ready Kubernetes deployment setup for the EasyShop e-commerce application.

The infrastructure is designed using Kubernetes best practices including:

- ✅ Namespace Isolation
- ✅ Priority Class Configuration
- ✅ Persistent Volumes & PVC (MongoDB)
- ✅ StatefulSet for MongoDB
- ✅ Deployment for Application & Redis
- ✅ Services (ClusterIP)
- ✅ Ingress Configuration
- ✅ ConfigMaps & Secrets Management
- ✅ GitOps Deployment using ArgoCD

## 🛠️ Tech Stack

- Kubernetes (K8s)
- Docker
- MongoDB
- Redis
- ArgoCD
- Ingress Controller
- YAML Manifests

## 📂 Project Structure

- Namespace & Priority Class Setup
- Database Layer (MongoDB StatefulSet + PVC)
- Cache Layer (Redis Deployment)
- Application Deployment
- Service Exposure
- Ingress Routing
- SSL Certificate Configuration
- ArgoCD Integration

## 🎯 Objective

The goal of this project is to simulate a real production environment deployment of a microservices-based application using Kubernetes and GitOps methodology.
