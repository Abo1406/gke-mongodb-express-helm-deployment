# MongoDB ReplicaSet on GKE with Mongo-Express

[![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.27+-326CE5?logo=kubernetes&logoColor=white)](https://kubernetes.io/)
[![Helm](https://img.shields.io/badge/Helm-v3.10+-0F1689?logo=helm&logoColor=white)](https://helm.sh/)
[![MongoDB](https://img.shields.io/badge/MongoDB-7.0+-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/)

Production-grade deployment of MongoDB ReplicaSet with Mongo-Express admin UI on Google Kubernetes Engine. Managed through Helm charts with persistent storage and secure ingress access.

![deepseek_mermaid_20250625_3e1230](https://github.com/user-attachments/assets/71de462d-3000-4e71-8999-d8bacd0cf08c)

## Features
🛡️ MongoDB ReplicaSet (3-node with Arbiter)

🌐 Mongo-Express Admin UI (Ingress-exposed)

🔐 Secret Management for credentials

📦 Helm-driven deployments

⚙️ Persistent volumes using GKE standard StorageClass

## Prerequisites
### Google Cloud Account with billing enabled
### GKE cluster with:
 * Minimum 3 nodes (e2-medium recommended)
 * Enabled Ingress controller

### Installed tools:
* gcloud CLI
* kubectl (v1.25+)
* helm (v3.10+)


