# 🚀 Automated Static Website Deployment via Jenkins CI/CD Pipeline to AWS S3

An end-to-end DevOps project showcasing an automated Continuous Integration and Continuous Deployment (CI/CD) pipeline. This setup automatically deploys a static website hosted on GitHub to an AWS S3 bucket whenever changes are pushed to the repository.

---

## 🏗️ Architecture Overview



[ Local Dev / Git Push ] ──► [ GitHub Repository ] ──► [ Webhook Trigger ] ──► [ Jenkins CI/CD (AWS EC2) ] ──► [ AWS S3 Bucket ] ──► [ Live Website ]




1. **Source Control:** HTML/CSS content managed in GitHub.
2. **Automation Trigger:** GitHub Webhooks trigger Jenkins on every code push to the `main` branch.
3. **CI/CD Server:** Jenkins running on an AWS EC2 instance processes the pipeline stages.
4. **Deployment Target:** Automated sync using AWS CLI (`aws s3 sync`) to an AWS S3 bucket configured for Static Website Hosting.

---

## 🛠️ Tech Stack & Prerequisites

* **Version Control:** Git & GitHub
* **CI/CD Tool:** Jenkins Pipeline (Groovy DSL)
* **Cloud Platform:** Amazon Web Services (AWS)
  * **AWS EC2:** Ubuntu Server hosting Jenkins
  * **AWS S3:** Bucket hosting public static website content
  * **AWS IAM:** Access credentials for Jenkins to publish to S3
* **CLI Tools:** AWS CLI (`aws s3 sync`)

---

## ⚙️ Pipeline Configuration

The pipeline is defined as code in a `Jenkinsfile`:

```groovy
pipeline {
    agent any

    stages {
        // Step 1: Pull the latest source code from GitHub
        stage('Checkout') {
            steps {
                git branch: 'main', url: '[https://github.com/Mohammedadil0067-sys/Jenkins.git](https://github.com/Mohammedadil0067-sys/Jenkins.git)'
            }
        }
        
        // Step 2: Deploy website files directly to the target S3 bucket
        stage('Deploy to S3') {
            steps {
                sh 'aws s3 sync . s3://jens3kins --exclude ".git/*" --exclude "Jenkinsfile"'
            }
        }
    }
}






