pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Install dependencies for both frontend and backend
                    sh 'npm install --prefix frontend'
                    sh 'npm install --prefix backend'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // Run tests for both frontend and backend
                    sh 'npm test --prefix frontend'
                    sh 'npm test --prefix backend'
                }
            }
        }

        stage('Build Application') {
            steps {
                script {
                    // Build the frontend and backend applications
                    sh 'npm run build --prefix frontend'
                    sh 'npm run build --prefix backend'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy using Docker Compose
                    sh 'docker-compose up --build -d'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed!'
        }
    }
}
