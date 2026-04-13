# 🚀 CI/CD Pipeline using Jenkins, Docker, and Terraform (Local Setup)

## 📌 Project Overview

This project demonstrates a complete CI/CD pipeline using **Jenkins**, **Docker Desktop**, and **Terraform** on a local machine. The pipeline automates building, testing, and running a Node.js application inside Docker containers, along with infrastructure simulation using Terraform.

---

## 🛠️ Tools & Technologies Used

* Jenkins (CI/CD Automation)
* GitHub (Source Code Management)
* Docker Desktop (Containerization)
* Terraform (Infrastructure as Code - Local)
* Node.js (Application Runtime)
* Git (Version Control)

---

## 📁 Project Structure

```
nodejs-demo-app/
│
├── app.js
├── package.json
├── Dockerfile
├── Jenkinsfile
├── main.tf
└── README.md
```

---

## ⚙️ How It Works

### 1. Jenkins CI/CD Pipeline

* Jenkins pulls code from GitHub
* Installs dependencies
* Builds Docker image
* Runs container locally
* Executes Terraform scripts

---

### 2. Docker Setup

The application is containerized using Docker Desktop.

#### Build Image:

```bash
docker build -t nodejs-app .
```

#### Run Container:

```bash
docker run -p 3000:3000 nodejs-app
```

---

### 3. Terraform (Local Infrastructure Simulation)

Terraform is used to create local resources (not cloud-based).

#### Initialize:

```bash
terraform init
```

#### Apply:

```bash
terraform apply -auto-approve
```

---

## 🔄 Jenkins Pipeline Flow

1. Clone repository from GitHub
2. Install dependencies (`npm install`)
3. Build Docker image
4. Run Docker container
5. Execute Terraform scripts

---

## 📄 Jenkinsfile Example

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t nodejs-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 nodejs-app'
            }
        }

        stage('Terraform') {
            steps {
                sh 'terraform init'
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
```

---

## 🚀 Features

* Automated CI/CD pipeline
* Containerized application using Docker
* Infrastructure automation using Terraform (local)
* GitHub integration with Jenkins
* Fully local development setup

---

## ❌ Challenges Faced

* Jenkins not detecting correct branch (`master` → fixed to `main`)
* Docker permission issues (resolved by starting Docker Desktop)
* Jenkinsfile naming issue (must be exact: `Jenkinsfile`)

---

## 📌 Conclusion

This project demonstrates a complete DevOps workflow using Jenkins, Docker, and Terraform on a local system, enabling automation of build, test, and deployment processes.

---

## 👨‍💻 Author

Your Name: __________
GitHub: https://github.com/your-username

---
