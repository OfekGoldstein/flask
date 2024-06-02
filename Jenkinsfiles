pipeline {
    agent any
    
    environment {
        // Define environment variables
        DOCKER_IMAGE_NAME = 'your_docker_image_name'
        CONTAINER_NAME = 'your_container_name'
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
                // Run tests (e.g., using a testing framework or tools)
                script {
                    sh 'echo "Running tests..."'
                    // Example: run unit tests for your Flask application
                    sh 'python -m unittest discover tests'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the website
                script {
                    // Start Docker container with the built image
                    docker.image(DOCKER_IMAGE_NAME).run('-p 80:80', '--name', CONTAINER_NAME)
                }
            }
        }
    }
    
    post {
        always {
            // Clean up resources after the pipeline run
            script {
                // Stop and remove Docker container
                docker.stop(CONTAINER_NAME)
                docker.remove(CONTAINER_NAME)
            }
        }
    }
}
