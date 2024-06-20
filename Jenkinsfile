pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout your repository
                checkout scm
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image using Dockerfile from repository
                    def dockerImage = docker.build("hello-world:latest", ".")
                }
            }
        }
        
        stage('Run Docker Container') {
            steps {
                script {
                    // Run the Docker container
                    docker.image("hello-world:latest").run()
                }
            }
        }
    }
    
    post {
        always {
            // Clean up: Stop and remove the container after execution
            script {
                docker.image("hello-world:latest").stop()
                docker.image("hello-world:latest").remove(force: true)
            }
        }
    }
}
