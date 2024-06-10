---
title: "Setting Up SSL with Let's Encrypt (Nginx)"
tags: ["ssl", "let's encrypt", "nginx"]
author: "Runbook.site"
---

This runbook describes how to set up SSL for a website using Let's Encrypt and Nginx.

## Prerequisites
- Access to the server
- Nginx installed
- Domain name pointing to the server

## Steps

1. **Install Certbot**
```bash
sudo apt update
sudo apt install -y certbot python3-certbot-nginx
```
2. **Obtain SSL Certificate**
```bash
sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com
```
3. **Follow Certbot Prompts**
- Enter your email address.
- Agree to the terms of service.
- Choose to redirect HTTP to HTTPS.

4. **Renew SSL Certificates**
```bash
sudo certbot renew --dry-run
```

## Verification
- Check your website at https://yourdomain.com.
- Verify that the SSL certificate is correctly installed and valid.

