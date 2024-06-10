---
title: "Configuring Nginx as a Reverse Proxy"
tags: ["nginx", "reverse proxy", "web server", "ubuntu", "linux"]
author: "Runbook.site"
---

This runbook outlines the steps to configure Nginx as a reverse proxy for an application.

## Prerequisites
- Access to the server
- Nginx installed
- Application running on a specific port

## Steps

1. **Install Nginx**
```bash
sudo apt install -y nginx
```
2. **Create Nginx Configuration File**
```bash
sudo nano /etc/nginx/sites-available/app_proxy
```
3. **Add the Configuration**
```nginx
server {
    listen 80;

    server_name yourdomain.com;

    location / {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```
4. **Enable the Configuration**
```bash
sudo ln -s /etc/nginx/sites-available/app_proxy /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl restart nginx
```

## Verification
- Check the application at http://yourdomain.com.
- Ensure Nginx is passing traffic to the application correctly.