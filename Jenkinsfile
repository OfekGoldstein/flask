pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE_NAME = Dockerfile
        CONTAINER_NAME = Jenkins
    }
    
    stages {
        stage('Build') {
            steps {
                // Build Docker image
                script {
                    docker.build DOCKER_IMAGE_NAME
                }
            }
        }
        
        stage('Test') {
            steps {
                // Run tests
                script {
                    sh 'echo "Running tests..."'
                    // Add your custom test commands here
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the application
                script {
                    sh 'echo "Deploying application..."'
                    // Add your custom deployment commands here
                }
            }
        }
    }
    
    post {
        always {
            script {
                // Clean up resources
                // Stop and remove Docker container
                docker.stop(CONTAINER_NAME)
                docker.remove(CONTAINER_NAME)
            }
        }
    }
}
