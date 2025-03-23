pipeline {
    agent any
    environment {
        // Jenkins credential ID for Docker Hub (ensure this exists in Jenkins)
        DOCKERHUB_CREDENTIALS = credentials('anshulnp-dockerhub')
        // Docker image name and tag (pushes to your Docker Hub repository)
        IMAGE_NAME = "anshulnp/dockerfile:latest"
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your GitHub repository on the main branch.
                git url: 'https://github.com/SRCEM-AIM-Class-A/A14_AnshulParate_DjangoApp.git', branch: 'main'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image using the Dockerfile in sampleProject1 and set sampleProject1 as the build context.
                    dockerImage = docker.build("${env.IMAGE_NAME}", "-f Dockerfile .")
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                script {
                    // Log in to Docker Hub using the provided credentials and push the built image.
                    docker.withRegistry('https://index.docker.io/v1/', env.DOCKERHUB_CREDENTIALS) {
                        dockerImage.push()
                    }
                }
            }
        }
    }
}