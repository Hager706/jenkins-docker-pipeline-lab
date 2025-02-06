pipeline {
    agent any
    environment {
        DOCKER_HUB_CREDENTIALS = 'docker' // Use the ID you set in Jenkins credentials
        DOCKER_IMAGE_NAME = 'hagert/app' // Replace with your Docker Hub username and image name
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
