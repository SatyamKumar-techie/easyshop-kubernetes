# 🚀 EasyShop Kubernetes Deployment

A production-style Kubernetes deployment of the EasyShop application using MongoDB, Redis, HPA, Ingress, TLS and ArgoCD (GitOps approach).

---

## 🧰 Tech Stack

- Kubernetes
- KIND (Local Cluster)
- MongoDB (StatefulSet)
- Redis
- Deployment & Services
- HPA (Horizontal Pod Autoscaler)
- Ingress (Nginx)
- TLS (Self-Signed Issuer)
- ArgoCD
- Kustomize

---

## 🏗 Architecture Components

- Namespace
- ConfigMap & Secrets
- Persistent Volume (PV) & Persistent Volume Claim (PVC)
- MongoDB StatefulSet
- EasyShop Deployment (2 replicas)
- HPA (2–5 replicas auto scaling)
- Migration Job
- Redis Deployment
- Ingress Controller
- TLS Certificate
- ArgoCD Application (GitOps)

---

# 🛠 Step-by-Step Deployment Flow

## 1️⃣ Create KIND Cluster

```bash
kind create cluster --config 00-kind-config.yaml
```

---

## 2️⃣ Create Namespace

```bash
kubectl apply -f 01-namespace.yaml
```

---

## 3️⃣ Create Storage (MongoDB PV & PVC)

```bash
kubectl apply -f 02-mongodb-pv.yaml
kubectl apply -f 03-mongodb-pvc.yaml
```

---

## 4️⃣ Apply Configurations (ConfigMap & Secrets)

```bash
kubectl apply -f 04-configmap.yaml
kubectl apply -f 05-secrets.yaml
```

---

## 5️⃣ Deploy MongoDB (StatefulSet)

```bash
kubectl apply -f 06-mongodb-service.yaml
kubectl apply -f 07-mongodb-statefulset.yaml
```

Verify:

```bash
kubectl get pods -n easyshop
```

---

## 6️⃣ Run Database Migration Job

```bash
kubectl apply -f 12-migration-job.yaml
```

Check Job:

```bash
kubectl get jobs -n easyshop
```

---

## 7️⃣ Deploy EasyShop Application

```bash
kubectl apply -f 08-easyshop-deployment.yaml
kubectl apply -f 09-easyshop-service.yaml
```

---

## 8️⃣ Deploy Redis

```bash
kubectl apply -f 13-redis-service.yaml
kubectl apply -f 14-redis-deployment.yaml
```

---

## 9️⃣ Configure Ingress

```bash
kubectl apply -f 10-ingress.yaml
```

Check Ingress:

```bash
kubectl get ingress -n easyshop
```

---

## 🔟 Enable HPA (Auto Scaling)

```bash
kubectl apply -f 11-hpa.yaml
```

Verify scaling:

```bash
kubectl get hpa -n easyshop
```

---

## 1️⃣1️⃣ Setup TLS (Self-Signed Issuer)

```bash
kubectl apply -f selfsigned-issuer.yaml
kubectl apply -f easyshop-certificate.yaml
```

---

## 1️⃣2️⃣ Apply ArgoCD (GitOps)

```bash
kubectl apply -f argocd/
```

---

# 📊 Final Verification

```bash
kubectl get all -n easyshop
kubectl get ingress -n easyshop
kubectl get hpa -n easyshop
```

---

# 📈 Auto Scaling

HPA automatically scales pods between 2–5 replicas based on CPU usage.

---

# 👨‍💻 Author

**Satyam Kumar**  
DevOps Enthusiast 🚀  
GitHub: https://github.com/SatyamKumar-techie
