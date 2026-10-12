pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add your build commands here (e.g., npm install,mvn clean package)
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test commands here (e.g., npm test)
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application to production...'
                // Add your deployment commands here
            }
        }
    }
}
