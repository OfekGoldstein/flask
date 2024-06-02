pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Build Docker image
                script {
                    docker.build 'your_docker_image_name'
                }
            }
        }
        
        stage('Test') {
            steps {
                // Run tests
                // Add your test steps here
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the application
                // Add your deployment steps here
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
