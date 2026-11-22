
pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/AlekhyaKolisetti/DevOps-Two-Tier-Flask-App-Azure.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:latest .'
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                // Stop existing containers if they are running
                sh 'docker compose down || true'

                // Build and start the application containers
                sh 'docker compose up -d --build'
            }
        }
    }
}
