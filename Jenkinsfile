pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/nainwaya-harsh/Jenkins-CI-CD.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build needed for static site'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                rm -rf /var/www/html/*
                cp index.html style.css script.js /var/www/html/
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment successful'
        }
        failure {
            echo 'Deployment failed'
        }
    }
}
