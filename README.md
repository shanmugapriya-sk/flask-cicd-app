# CI/CD Pipeline for a Dockerized Flask App

A fully automated **CI/CD pipeline** that builds, containerizes, and deploys a Flask web application on every code push — **no manual deployment required**.

## Live Demo

**Application:** https://flask-cicd-app-t0eo.onrender.com

## Docker Hub Image

**Docker Hub:** https://hub.docker.com/r/shanmugapriya01/flask-cicd-app

---

# Overview

This project demonstrates a complete **DevOps CI/CD workflow** using **GitHub Actions, Docker, Docker Hub, and Render**.

Whenever new code is pushed to the **main** branch:

- GitHub Actions automatically starts the pipeline
- A new Docker image is built
- The image is pushed to Docker Hub
- Render detects the update from GitHub
- The application is automatically redeployed

No manual deployment is needed.

---

# Architecture

```text
                Developer
                    │
        Push Code to GitHub (main)
                    │
                    ▼
        GitHub Actions Workflow
                    │
                    ▼
      Build Docker Image (Dockerfile)
                    │
                    ▼
     Push Image to Docker Hub Registry
                    │
                    ▼
    Render Detects New GitHub Commit
                    │
                    ▼
        Automatic Application Deploy
                    │
                    ▼
            Live Flask Application
```

---

# Tech Stack

| Technology | Purpose |
|------------|---------|
| Python | Programming Language |
| Flask | Web Framework |
| Docker | Containerization |
| GitHub Actions | CI/CD Automation |
| Docker Hub | Docker Image Registry |
| Render | Cloud Deployment |
| Git | Version Control |
| GitHub | Source Code Hosting |

---

# CI/CD Workflow

The deployment pipeline performs the following steps automatically:

1. Developer pushes code to the **main** branch.
2. GitHub Actions workflow is triggered.
3. GitHub Actions checks out the latest source code.
4. Docker image is built using the project's `Dockerfile`.
5. GitHub Actions logs into Docker Hub using encrypted GitHub Secrets.
6. Newly built Docker image is pushed to Docker Hub.
7. Render detects the GitHub update.
8. Render rebuilds and deploys the latest application.
9. Updated Flask application becomes available online.

---

# Project Structure

```text
flask-cicd-app/
│
├── .github/
│   └── workflows/
│       └── deploy.yml        # GitHub Actions Workflow
│
├── app.py                    # Flask Application
├── Dockerfile                # Docker Build Instructions
├── requirements.txt          # Python Dependencies
├── README.md                 # Documentation
└── .gitignore                # Git Ignore Rules
```

---

# Running the Project Locally

## 1. Clone the Repository

```bash
git clone https://github.com/shanmugapriya-sk/flask-cicd-app.git
```

---

## 2. Navigate into the Project

```bash
cd flask-cicd-app
```

---

## 3. Build the Docker Image

```bash
docker build -t flask-cicd-app .
```

---

## 4. Run the Docker Container

```bash
docker run -p 5000:5000 flask-cicd-app
```

---

## 5. Open in Browser

```
http://localhost:5000
```

---

# Docker Image

Build Docker image:

```bash
docker build -t flask-cicd-app .
```

Run container:

```bash
docker run -p 5000:5000 flask-cicd-app
```

List running containers:

```bash
docker ps
```

Stop container:

```bash
docker stop <container-id>
```

---

# GitHub Secrets Used

The following GitHub Secrets are configured for secure authentication:

| Secret | Description |
|---------|-------------|
| DOCKER_USERNAME | Docker Hub Username |
| DOCKER_PASSWORD | Docker Hub Access Token |

These credentials are securely stored in GitHub Secrets and are never exposed in the source code.

---

#  CI/CD Pipeline

The GitHub Actions workflow is located at:

```text
.github/workflows/deploy.yml
```

The workflow automatically:

- Checks out the repository
- Builds the Docker image
- Logs into Docker Hub
- Pushes the latest image
- Completes the CI/CD pipeline

---

# Deployment

The application is deployed on **Render**.

Render automatically watches the GitHub repository.

Whenever a new commit is pushed to the **main** branch, Render automatically:

- Pulls the latest source code
- Rebuilds the application
- Deploys the newest version

No manual deployment is required.

---

# Features

- Automated CI/CD Pipeline
- Dockerized Flask Application
- GitHub Actions Automation
- Docker Hub Integration
- Render Auto Deployment
- Secure GitHub Secrets
- Easy Local Setup
- Cloud Hosted Application

---

# Future Improvements

Some planned enhancements include:

- Add automated unit testing with **pytest**
- Integrate code quality checks using **flake8**
- Deploy Docker containers on **AWS EC2**
- Provision infrastructure using **Terraform**
- Add monitoring with **Prometheus** and **Grafana**
- Use **Gunicorn** as a production WSGI server
- Add Kubernetes deployment support
- Implement multi-stage Docker builds
- Add security scanning in the CI pipeline

---

# Note

This application is hosted on **Render Free Tier**.

Render automatically spins down inactive services after periods of inactivity.

If the application has been idle, the first request may take **30–60 seconds** while the service wakes up.

---

# Author

**Shanmugapriya**

GitHub: https://github.com/shanmugapriya-sk

Docker Hub: https://hub.docker.com/r/shanmugapriya01/flask-cicd-app

---

# Support

If you found this project useful, consider giving it a **Star** on GitHub.

It helps others discover the project and supports future improvements.

---
