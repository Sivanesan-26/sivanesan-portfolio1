# Portfolio Website Deployment with Docker, AWS EC2 & GitHub Actions

## Project Overview

This project demonstrates how to deploy a static portfolio website using Docker on an AWS EC2 instance and automate the Docker image build and push process using GitHub Actions.

The website is containerized using Docker, hosted on AWS EC2, and integrated with a Continuous Integration (CI) pipeline.

---

## Technologies Used

- HTML5
- CSS3
- Docker
- Nginx
- Git
- GitHub
- GitHub Actions
- Docker Hub
- AWS EC2 (Amazon Linux 2023)

---

## Project Architecture

```
Developer
    │
    ▼
VS Code
    │
git push
    │
    ▼
GitHub Repository
    │
    ▼
GitHub Actions (CI)
    │
    ├── Build Docker Image
    └── Push Image to Docker Hub
                    │
                    ▼
             Docker Hub Repository

(Manual Deployment)

Docker Hub
    │
    ▼
AWS EC2 Instance
    │
    ▼
Docker Container (Nginx)
    │
    ▼
Live Portfolio Website
```

---

## Features

- Responsive Portfolio Website
- Docker Containerization
- Hosted on AWS EC2
- Automated Docker Image Build
- Automated Docker Image Push to Docker Hub
- Continuous Integration using GitHub Actions

---

## Dockerfile

```dockerfile
FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80
```

---

## Deployment Steps

### 1. Clone Repository

```bash
git clone https://github.com/Sivanesan-26/sivanesan-portfolio1.git
cd sivanesan-portfolio1
```

### 2. Build Docker Image

```bash
docker build -t portfolio-website .
```

### 3. Run Docker Container

```bash
docker run -d -p 80:80 portfolio-website
```

### 4. Deploy to AWS EC2

- Launch Amazon Linux EC2 Instance
- Install Docker
- Clone Repository
- Build Docker Image
- Run Docker Container
- Allow HTTP (Port 80) in Security Group

---

## GitHub Actions Workflow

Whenever code is pushed to the **main** branch:

- Repository is checked out
- Docker image is built automatically
- Docker image is pushed to Docker Hub automatically

This automates the Continuous Integration (CI) process.

**Note:** The deployment to AWS EC2 is still manual. After a new Docker image is pushed to Docker Hub, the latest image must be pulled and the Docker container restarted on the EC2 instance.

---

## Docker Hub Repository

https://hub.docker.com/r/sivanesan19/portfolio-website

---

## GitHub Repository

https://github.com/Sivanesan-26/sivanesan-portfolio1

---

## Live Website

http://3.27.44.214

---

## Future Improvements

- Automate deployment to AWS EC2 using GitHub Actions (Continuous Deployment)
- Configure a custom domain
- Enable HTTPS using SSL/TLS
- Add monitoring and logging

---

## Author

**Sivanesan R**

GitHub: https://github.com/Sivanesan-26
Docker Hub: https://hub.docker.com/u/sivanesan19
