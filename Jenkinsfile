pipeline {
    agent any
    environment {
        DOCKER_HUB_CREDENTIALS = 'docker' // Change this to your Jenkins credentials ID
        DOCKER_IMAGE_NAME = 'myusername/myapp' // Change this to your Docker image name
    }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    docker.build("${env.DOCKER_IMAGE_NAME}:${env.BUILD_ID}")
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                script {
                    // Push the Docker image to Docker Hub
                    docker.withRegistry('https://registry.hub.docker.com', "${env.DOCKER_HUB_CREDENTIALS}") {
                        docker.image("${env.DOCKER_IMAGE_NAME}:${env.BUILD_ID}").push()
                    }
                }
            }
        }
    }
}
