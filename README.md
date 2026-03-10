# DevOps Capstone Project – Containerized Web Application Deployment

## Project Overview

This project demonstrates the implementation of a complete **DevOps lifecycle** for deploying a containerized web application using modern DevOps tools and practices.

The objective was to automate the **build, containerization, deployment, and scaling** of an application using **Docker, Jenkins, Kubernetes, and Terraform** while maintaining version control using **Git**.

The system ensures automated CI/CD pipelines and scalable container orchestration.

---

## Architecture

The architecture follows a CI/CD pipeline where:

1. Developers push code to GitHub.
2. Jenkins automatically triggers a pipeline.
3. Docker builds a custom container image.
4. The image is pushed to DockerHub.
5. Kubernetes pulls the image and deploys the application.
6. The application is exposed using a NodePort service.

---

## CI/CD Pipeline Workflow

The automated pipeline performs the following tasks:

1. Pulls the latest code from GitHub.
2. Builds a Docker image using the Dockerfile.
3. Pushes the Docker image to DockerHub.
4. Deploys the containerized application to a Kubernetes cluster.

---

## Technologies Used

### DevOps Tools

* Jenkins
* Docker
* Kubernetes
* Terraform

### Version Control

* Git
* GitHub

### Programming / Web

* HTML

### Container Registry

* DockerHub

### Infrastructure

* AWS Cloud

---

## Infrastructure Setup

Infrastructure is provisioned using **Terraform**.

Four worker nodes were used:

| Node    | Installed Software       |
| ------- | ------------------------ |
| Worker1 | Jenkins, Java            |
| Worker2 | Docker, Kubernetes       |
| Worker3 | Java, Docker, Kubernetes |
| Worker4 | Docker, Kubernetes       |

Configuration management was used to install required software across servers.

---

## Kubernetes Deployment

The application is deployed using Kubernetes with the following specifications:

* **Replicas:** 2
* **Service Type:** NodePort
* **Port:** 30008

This ensures the application is scalable and accessible externally.

---

## CI/CD Pipeline (Jenkins)

The Jenkins pipeline automates:

* Source code checkout
* Docker image build
* Docker image push to DockerHub
* Kubernetes deployment

Pipeline configuration is defined in the **Jenkinsfile**.

---

## Repository Files

| File            | Description                                 |
| --------------- | ------------------------------------------- |
| Dockerfile      | Defines container image for the application |
| Jenkinsfile     | CI/CD pipeline configuration                |
| deployment.yaml | Kubernetes deployment configuration         |
| service.yaml    | Kubernetes service configuration            |
| index.html      | Sample web application                      |

---

## Key Features

* Automated CI/CD pipeline
* Containerized application deployment
* Kubernetes orchestration
* Infrastructure as Code using Terraform
* Scalable container deployment

---

## Author

**Akshatha**

DevOps & Cloud Enthusiast
AWS | Docker | Kubernetes | Terraform | Jenkins
