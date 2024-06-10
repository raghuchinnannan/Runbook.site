---
title: "Installing Docker"
tags: ["docker", "containerization", "installation"]
author: "Runbook.site"
---

This runbook explains how to install Docker on a Linux server.

## Prerequisites
- Access to the server
- Root or sudo privileges

## Steps

1. **Update Package List**
```bash
sudo apt update
```
2. **Install Required Packages**
```bash
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```
3. **Add Docker GPG Key**
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
4. **Add Docker Repository**
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
5. **Install Docker**
```bash
sudo apt update
sudo apt install -y docker-ce
```

6. **Start and Enable Docker**
```bash
sudo systemctl start docker
sudo systemctl enable docker
```

## Verification
- Check Docker version:
```bash
docker --version
```
- Run a test container:
```bash
sudo docker run hello-world
```