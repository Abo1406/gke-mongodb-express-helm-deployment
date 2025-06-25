# MongoDB ReplicaSet on GKE with Mongo-Express

[![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.27+-326CE5?logo=kubernetes&logoColor=white)](https://kubernetes.io/)
[![Helm](https://img.shields.io/badge/Helm-v3.10+-0F1689?logo=helm&logoColor=white)](https://helm.sh/)
[![MongoDB](https://img.shields.io/badge/MongoDB-7.0+-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/)

Production-grade deployment of MongoDB ReplicaSet with Mongo-Express admin UI on Google Kubernetes Engine. Managed through Helm charts with persistent storage and secure ingress access.

![deepseek_mermaid_20250625_3e1230](https://github.com/user-attachments/assets/71de462d-3000-4e71-8999-d8bacd0cf08c)

## Features
* 🛡️ MongoDB ReplicaSet (3-node with Arbiter)

* 🌐 Mongo-Express Admin UI (Ingress-exposed)

* 🔐 Secret Management for credentials

* 📦 Helm-driven deployments

* ⚙️ Persistent volumes using GKE standard StorageClass

## Prerequisites
### 1. Google Cloud Account with billing enabled
### 2. GKE cluster with:
 * Minimum 3 nodes (e2-medium recommended)
 * Enabled Ingress controller

### 3. Installed tools:
* gcloud CLI
* kubectl (v1.25+)
* helm (v3.10+)

## Deployment Steps
### 1. Clone Repository
```bash
git clone https://github.com/<your-username>/gke-mongodb-express-helm-deployment.git
cd gke-mongodb-express-helm-deployment
```
### 2. Deploy MongoDB
```bash
helm install mongodb bitnami/mongodb -f helm-values-mongo.yml
```
### 3. Create Secrets
```bash
kubectl apply -f secret.yml
```
### 4. Deploy Mongo-Express
```bash
kubectl apply -f mongo-express.yml
```
### 5. Configure Ingress
```bash
kubectl apply -f helm-ingress.yml
```

## Accessing Applications
### Mongo-Express Dashboard:
http://<INGRESS_IP> (Get IP with kubectl get ingress)
### MongoDB Connection:
mongodb://root:<PASSWORD>@mongodb-headless.default.svc.cluster.local:27017

## Verification
```bash
# Check all resources
kubectl get all,ingress,secret

# Monitor MongoDB statefulsets
kubectl get statefulset
```
## Cleanup
```bash
helm uninstall mongodb
kubectl delete -f mongo-express.yml,helm-ingress.yml,secret.yml
```
## Security Notes
* 🔑 Change default password in secret.yml for production

* 🔒 Enable TLS termination in helm-ingress.yml

* 🛑 Restrict Ingress access to authorized IPs

## License
MIT - See LICENSE
