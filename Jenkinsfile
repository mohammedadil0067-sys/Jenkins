pipeline {
    agent any

    stages {
        // Step 1: Pull the latest source code from the GitHub repository
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Mohammedadil0067-sys/Jenkins.git'
            }
        }
        
        // Step 2: Sync static website files from workspace directly to the AWS S3 bucket
        stage('Deploy to S3') {
            steps {
                sh 'aws s3 sync . s3://jens3kins --exclude ".git/*" --exclude "Jenkinsfile"'
            }
        }
    }
}
