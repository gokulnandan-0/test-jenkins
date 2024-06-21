pipeline {
    agent any
    stages {
        stage('Run Hello-World Docker Container') {
            steps {
                script {
                    docker.image('hello-world').inside {
                        sh 'echo "Hello, World from Docker!"'
                    }
                }
            }
        }
    }
}
