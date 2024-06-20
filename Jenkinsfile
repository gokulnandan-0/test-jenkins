pipeline {
    agent {
        docker { image 'docker:19.03.12' }
    }
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
