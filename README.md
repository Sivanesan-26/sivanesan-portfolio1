# Portfolio Website Deployment using Docker on AWS EC2

## Project Overview

This project demonstrates how to deploy a static portfolio website using Docker on an AWS EC2 instance. The website is containerized with Docker and served using the Nginx web server.

## Technologies Used

- HTML5
- CSS3
- Docker
- Nginx
- Git
- GitHub
- AWS EC2 (Amazon Linux 2023)

## Project Structure

```
.
├── Dockerfile
├── index.html
├── style.css
└── README.md
```

## Dockerfile

```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
```

## Deployment Steps

### 1. Launch an AWS EC2 Instance
- Create an Amazon Linux 2023 EC2 instance.
- Allow HTTP (Port 80) in the Security Group.

### 2. Install Docker

```bash
sudo dnf update -y
sudo dnf install docker -y
sudo systemctl enable docker
sudo systemctl start docker
```

### 3. Clone the Repository

```bash
git clone https://github.com/SivanesanR/sivanesan-portfolio1.git
cd sivanesan-portfolio1
```

### 4. Build the Docker Image

```bash
sudo docker build -t portfolio-website .
```

### 5. Run the Docker Container

```bash
sudo docker run -d -p 80:80 portfolio-website
```

### 6. Verify the Running Container

```bash
sudo docker ps
```

### 7. Access the Website

Open your browser and visit:

```
http://3.27.44.214
```

## Features

- Responsive portfolio website
- Docker containerized deployment
- Hosted on AWS EC2
- Served using Nginx
- Publicly accessible through EC2 Public IP

## GitHub Repository

https://github.com/SivanesanR/sivanesan-portfolio1

## Live Website

http://3.27.44.214

## Author

**Sivanesan R**

- GitHub: https://github.com/SivanesanR
