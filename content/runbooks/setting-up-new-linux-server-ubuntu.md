---
title: "Setting Up a New Linux Server"
tags: ["linux", "server", "setup", "ubuntu"]
author: "Runbook.site"
---

This runbook provides the steps to set up a new Linux server.

## Prerequisites
- Access to the server
- Root or sudo privileges

## Steps

1. **Update Package Lists**
   ```bash
   sudo apt update
    ```
2. **Upgrade Packages**
    ```bash
    sudo apt upgrade -y
    ```
3. **Install Common Utilities**
    ```bash
    sudo apt install -y curl wget git vim
    ```
4. **Set Up Firewall**
    ```bash
    sudo ufw allow OpenSSH
    sudo ufw enable
    ```
5. **Create a New User**
    ```bash
    sudo adduser newuser
    sudo usermod -aG sudo newuser
    ```
6. **Configure SSH Access**
    ```bash
    sudo cp /root/.ssh/authorized_keys /home/newuser/.ssh/
    sudo chown newuser:newuser /home/newuser/.ssh/authorized_keys
    ```

## Verification 
- Connect to the server using the new user.
- Check basic commands and utilities.