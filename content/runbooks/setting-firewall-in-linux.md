---
title: "Setting Up a Firewall"
tags: ["security", "firewall", "linux"]
author: "Runbook.site"
---

This runbook explains how to set up a firewall on a Linux server using UFW.

## Prerequisites
- Access to the server
- Root or sudo privileges

## Steps

1. **Install UFW**
```bash
sudo apt install -y ufw
```
2. **Allow SSH Connections**
```bash
sudo ufw allow OpenSSH
```
3. **Enable the Firewall**
```bash
sudo ufw enable
```
4. **Allow Other Essential Services**
```bash
sudo ufw allow http
sudo ufw allow https
```
5. **Check Firewall Status**
```bash
sudo ufw status verbose
```

## Verification
- Ensure SSH connection remains intact.
- Verify that the web server and other allowed services are accessible.