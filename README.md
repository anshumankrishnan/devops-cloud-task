# 🚀 DevOps Cloud Infrastructure Deployment

## 📌 Project Overview

This project demonstrates a complete DevOps workflow including containerization, CI/CD automation, cloud deployment, and monitoring using free-tier tools.

The application is a simple NGINX-based web app deployed using Docker and hosted on a cloud platform with automated CI/CD pipelines and monitoring integration.

---

## 🎯 Objectives

* Learn Linux server and Git basics
* Build and containerize an application using Docker
* Deploy application on cloud (Render / Railway / Fly.io)
* Implement CI/CD using GitHub Actions
* Configure monitoring using Grafana Cloud & Prometheus
* Understand DevOps end-to-end workflow

---

## 🛠️ Technologies Used

* HTML
* Docker
* Docker Compose
* Git & GitHub
* GitHub Actions
* NGINX
* Render Cloud (Free Tier)
* Grafana Cloud (Free Tier)
* Prometheus (Optional)
* Cloudflare (Optional for DNS/SSL)

---

## 📁 Project Structure

```
devops-cloud-task/
│
├── index.html
├── Dockerfile
├── docker-compose.yml
├── README.md
│
├── .github/
│   └── workflows/
│       └── deploy.yml
│
└── screenshots/
```

---

## 🧑‍💻 Local Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/your-username/devops-cloud-task.git
cd devops-cloud-task
```

### 2. Build Docker Image

```bash
docker compose up --build
```

### 3. Run Application

Open in browser:

```
http://localhost
```

Expected Output:

```
DevOps Deployment Successful
```

---

## 🐳 Docker Setup

### Dockerfile

```dockerfile
FROM nginx:latest
COPY . /usr/share/nginx/html
```

### docker-compose.yml

```yaml
version: '3'

services:
  web:
    build: .
    ports:
      - "80:80"
```

---

## ☁️ Cloud Deployment (Render)

### Steps:

1. Push code to GitHub
2. Go to Render Dashboard
3. Click "New Web Service"
4. Connect GitHub repository
5. Select:

   * Environment: Docker
   * Branch: main
6. Click Deploy

### Live URL:

```
https://your-app-name.onrender.com
```

---

## 🔁 CI/CD Pipeline (GitHub Actions)

Workflow automatically runs on every push to main branch.

### Workflow File:

`.github/workflows/deploy.yml`

```yaml
name: Docker Build Test

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Code
        uses: actions/checkout@v3

      - name: Build Docker Image
        run: docker build -t devops-task .
```

---

## 📊 Monitoring Setup

### Tools Used:

* Grafana Cloud
* Prometheus (optional)

### Metrics Monitored:

* CPU Usage
* Memory Usage
* Container Status
* Application Health

---

## 🔐 Security (Optional Enhancements)

* HTTPS via Cloudflare SSL
* Secure DNS configuration
* Firewall rules in cloud deployment

---

## 📸 Screenshots

Screenshots are included in the `/screenshots` folder:

* GitHub repository
* Docker running locally
* Render deployment success
* Live application output
* GitHub Actions success
* Grafana dashboard

---

## 🌐 Live Project

```
https://your-render-app-url.onrender.com
```

---

## 📌 GitHub Repository

```
https://github.com/your-username/devops-cloud-task
```

---

## 📚 Learning Outcomes

* Docker containerization
* CI/CD pipeline setup
* Cloud deployment workflow
* GitHub Actions automation
* Monitoring & observability
* DevOps best practices

---

## 🏁 Conclusion

This project demonstrates a full end-to-end DevOps pipeline from development to deployment and monitoring using free tools and cloud services.
