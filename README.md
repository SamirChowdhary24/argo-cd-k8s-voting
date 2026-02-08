
# GitOps-Based Kubernetes Deployment with Argo CD on AWS EC2

## 📌 Project Overview
This project demonstrates an **end-to-end GitOps workflow** where a microservices-based application is deployed and managed on a Kubernetes cluster using **Argo CD**.  
The Kubernetes cluster is created using **KIND (Kubernetes IN Docker)** and hosted on an **AWS EC2 instance**.  
The project also includes **cluster visualization using Kubernetes Dashboard** and external access to services using **NodePort**.

---

## 🛠 Tools & Technologies Used

- **AWS EC2** – Cloud virtual machine to host the environment  
- **Docker** – Container runtime for Kubernetes nodes  
- **KIND** – Lightweight Kubernetes cluster inside Docker  
- **Kubernetes** – Container orchestration platform  
- **kubectl** – CLI to interact with Kubernetes  
- **Argo CD** – GitOps-based continuous deployment tool  
- **Kubernetes Dashboard** – Web UI for cluster monitoring  
- **GitHub** – Source of Kubernetes manifests  

---

## 🔄 Workflow Summary

1. Launch an AWS EC2 instance  
2. Install Docker and Kubernetes tooling  
3. Create a multi-node Kubernetes cluster using KIND  
4. Install and access Argo CD  
5. Deploy a microservices application using GitOps  
6. Expose services externally using NodePort  
7. Monitor the cluster using Kubernetes Dashboard  

---

## ☁️ Infrastructure Setup

### 1. AWS EC2 Instance
- Instance Type: `t2.medium`
- OS: Ubuntu
- Storage: 15 GB
- Security Group configured to allow:
  - Argo CD UI
  - Kubernetes Dashboard
  - NodePort services

📸 **Screenshot:** EC2 Security Group inbound rules

---

## 🐳 Docker Installation

```bash
sudo apt-get update
sudo apt-get install docker.io -y
```
Fix Docker permission issue
```bash
sudo usermod -aG docker $USER
newgrp docker
```
## ☸️ Kubernetes Cluster Setup using KIND
Install KIND
Script used: scripts/install_kind.sh

to make .sh file executable.
```bash
chmod +x install_kind.sh
./install_kind.sh
```

## Create Kubernetes Cluster
Configuration file: kubernetes/kind-cluster-config.yaml

```bash
kind create cluster --name my-cluster --config kind-cluster-config.yaml
```

![alt text](<WhatsApp Image 2026-01-26 at 4.05.15 PM.jpeg>)

