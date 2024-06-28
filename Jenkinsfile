pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from the repository
                git 'https://your-repo-url.git'
            }
        }
        
        stage('Build and Run React App') {
            steps {
                script {
                    // Build and run only the react-app service using the new compose file
                    sh 'docker-compose -f docker-compose.frontend.yml up -d react-app'
                }
            }
        }
    }
    
    post {
        always {
            // Clean up
            script {
                sh 'docker-compose -f docker-compose.frontend.yml down'
            }
        }
    }
}
