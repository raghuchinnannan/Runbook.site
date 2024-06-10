---
title: "Deploying a Web Application"
tags: ["deployment", "web application", "nodejs"]
author: "Runbook.site"
---

This runbook outlines the steps to deploy a web application.

## Prerequisites
- Access to the repository
- Deployment credentials

## Steps

1. **Clone the Repository**
```bash
git clone https://github.com/your-repo/web-app.git
cd web-app
```
2. **Install Dependencies**
```bash
npm install
```
3. **Run Tests**
```bash
npm test
```
4. **Build the Application**
```bash
npm run build
```
5. **Deploy to Server**
```bash
scp -r build/ user@server:/var/www/web-app
```
## Verification
- Check the web application at http://your-server-address.
- Ensure all endpoints are working.