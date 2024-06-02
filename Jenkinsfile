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
                script {
                    sh 'echo "Running tests..."'
                    // Add your custom test commands here
                    // For example, you can run unit tests for your application
                    // e.g., npm test for a Node.js application
                    // or python -m unittest for a Python application
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Deploy the application
                script {
                    sh 'echo "Deploying application..."'
                    // Add your custom deployment commands here
                    // For example, you can deploy the Docker image to a server
                    // e.g., docker push to a Docker registry
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
