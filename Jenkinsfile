
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code from Git...'
            }
        }

        stage('Deploy to S3') {
            steps {
                echo 'Uploading files to AWS S3...'
                sh 'aws s3 sync . s3://jens3kins --exclude ".git/*" --exclude "Jenkinsfile"'
            }
        }
    }
}

