# 🚀 Terraform Docker Deployment on AWS EC2

This project demonstrates how to use **Terraform** to spin up a **Docker container** (like NGINX) on a **local machine or AWS EC2 instance**. It exposes the container on port `8000` and allows access via the public IP.

---

## 📋 Prerequisites

- Docker installed and running
- Terraform installed
- User added to the `docker` group (`sudo usermod -aG docker $USER && newgrp docker`)
- Port `8000` open in the EC2 security group

---
## ⚙️ Install Terraform $ docker 

```bash
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
```
```bash
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null
```
```bash
gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
```
```bash
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
```
```bash
sudo apt update
sudo apt-get install terraform
```
## Install Docker ( if not installed )
```bash
sudo apt update
sudo apt install docker.io -y
```

## ⚙️ Setup Instructions

```bash
git clone https://github.com/vivekdalsaniya12/nginx-terraform.git
cd nginx-terraform
terraform init
terraform plan
terraform apply
```
 
## Verify the Container Is Running

`docker ps`


## Destroy the Infrastructure

`terraform destroy`

## modify infra ( Terraform will detect changes and apply them automatically. )

`terraform apply`
