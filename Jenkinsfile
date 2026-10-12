pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the website...'
                // Example: npm install && npm run build
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example: npm test
            }
        }

        stage('Deploy to Web Server') {
            steps {
                echo 'Deploying to website directory...'
                // Example for copying files to an Apache/Nginx web root on your server:
                // sh 'scp -r dist/* user@your-server-ip:/var/www/html/'
            }
        }
    }
}
