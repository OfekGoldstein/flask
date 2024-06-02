pipeline {
    agent any
    
    // Import Docker global variable
    import org.jenkinsci.plugins.docker.workflow.*

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
            // Clean up resources
            script {
                // Stop and remove Docker container
                docker.stop(CONTAINER_NAME)
                docker.remove(CONTAINER_NAME)
            }
        }
    }
}
