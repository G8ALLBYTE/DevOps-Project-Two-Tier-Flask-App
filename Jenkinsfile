pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                // Clone from GitHub
                git branch: 'main', url: 'https://github.com/G8ALLBYTE/DevOps-Project-Two-Tier-Flask-App.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:latest .'
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                sh 'docker compose down || true'
                sh 'docker compose up -d --build'
            }
        }
    }
}
