AKS Terraform Lab
This repository contains a simple, production‑style Terraform configuration to deploy an Azure Kubernetes Service (AKS) cluster.
It is designed as a hands‑on learning lab for SRE, DevOps, and Cloud Engineering workflows.
---
📌 Features
Deploys an AKS cluster using Terraform
Creates:
Resource Group
Log Analytics Workspace
AKS Cluster (System Node Pool)
Enables Azure Monitor / Container Insights
Uses System‑Assigned Managed Identity
Clean, minimal, easy‑to‑extend structure
---
📁 Repository Structure
aks-terraform-lab/
│
├── main.tf
├── providers.tf
├── variables.tf
├── outputs.tf
├── terraform.tfvars
├── README.md
└── .gitignore

---
🚀 Prerequisites
Make sure the following tools are installed:
Azure CLI
Terraform ≥ 1.3
kubectl
An active Azure subscription
Login to Azure:
az login

---
🛠 Deployment Steps
1. Initialize Terraform
terraform init

2. Validate the configuration
terraform validate

3. Preview the changes
terraform plan

4. Apply and deploy AKS
terraform apply

Type yes when prompted.
---
🔗 Connect to the AKS Cluster
Once the deployment completes:
az aks get-credentials \
  --resource-group rg-aks-lab \
  --name aks-lab-cluster

Verify the nodes:
kubectl get nodes

---
🌐 Deploy a Test Application
Deploy NGINX:
kubectl create deployment nginx --image=nginx
kubectl expose deployment nginx --port=80 --type=LoadBalancer

Get the external IP:
kubectl get svc

Open the IP in your browser to confirm the deployment.
---
🧹 Cleanup
To remove all resources:
terraform destroy

--
