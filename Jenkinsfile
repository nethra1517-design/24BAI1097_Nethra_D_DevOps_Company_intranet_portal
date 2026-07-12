pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t employee-intranet .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f employee-intranet-container || exit 0'
                bat 'docker run -d -p 8081:80 --name employee-intranet-container employee-intranet'
            }
        }

    }
}