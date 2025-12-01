Automated CI Pipeline Using Jenkins & Docker

This project demonstrates a fully automated Continuous Integration (CI) pipeline using Jenkins, GitHub, and Docker. The pipeline automatically builds a Docker image whenever new code is pushed to the GitHub repository.

🚀 Project Overview

This repository contains:

A simple Python application (app.py)

A Dockerfile to containerize the app

A Jenkinsfile defining the CI pipeline

The Jenkins pipeline is configured to:

Pull the latest code from GitHub

Build a Docker image

Print a success message

Trigger automatically on every GitHub commit (via Poll SCM)

🛠️ Technologies Used

Jenkins (Pipeline + SCM integration)

GitHub

Docker

Python

Windows PowerShell / CMD

📁 Repository Structure
sara-jenkins-demo/
│
├── app.py
├── Dockerfile
└── Jenkinsfile

🧪 Pipeline Stages
1️⃣ Build Docker Image

Builds a Docker image using the code in this repository.

2️⃣ Success Message

Prints “Build Successful!” if the pipeline completes without errors.

🐳 Jenkinsfile (Windows-Compatible)
pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    bat 'docker build -t sara/demo-app:latest .'
                }
            }
        }

        stage('Success Message') {
            steps {
                echo 'Build Successful!'
            }
        }
    }
}

🔄 Automatic Trigger (CI)

Jenkins is configured to automatically run the pipeline through:

Poll SCM: * * * * *


This checks GitHub every minute and runs the pipeline when new commits are found.

📦 How to Run Locally

Clone the repository:

git clone https://github.com/SaraKolas/sara-jenkins-demo.git


Build Docker image manually:

docker build -t sara/demo-app:latest .


Run the container:

docker run sara/demo-app:latest

🙌 Author

Sara Kolas
A hands-on DevOps enthusiast focusing on CI/CD, cloud, and automation.
