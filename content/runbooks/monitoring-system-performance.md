---
title: "Monitoring System Performance"
tags: ["monitoring", "performance", "linux"]
author: "Runbook.site"
---

This runbook provides steps to monitor system performance on a Linux server.

## Prerequisites
- Access to the server

## Steps

1. **Check CPU Usage**
```bash
top
```
2. **Check Memory Usage**
```bash
free -h
```
3. **Check Disk Usage**
```bash
df -h
```
4. **Check Network Usage**
```bash
iftop
```
5. **Install Monitoring Tools (Optional)**
```bash
sudo apt install -y htop glances nload
```

6. **Run Monitoring Tools**
```bash
htop
glances
nload
```

## Verification
- Ensure system resources are within acceptable limits.
- Identify and troubleshoot any bottlenecks or issues. 