pipeline {
    agent any

    parameters {
        string(name: 'IMAGE_TAG', defaultValue: 'latest', description: 'Docker image tag')
        booleanParam(name: 'PUSH_IMAGE', defaultValue: true, description: 'Push image to Docker Hub?')
    }

    environment {
        IMAGE_NAME = "devopssteps/my-app-15"
    }

    stages {

        stage('Clone Code') {
            steps {
                echo 'Cloning code...'
                checkout scm
            }
        }

        stage('Build Image') {
            steps {
                echo "Building Docker image: ${IMAGE_NAME}:${params.IMAGE_TAG}"
                // sh "docker build -t ${IMAGE_NAME}:${params.IMAGE_TAG} ."
            }
        }

        stage('Push Image') {
            when {
                expression { return params.PUSH_IMAGE }
            }
            steps {
                echo "Pushing Docker image: ${IMAGE_NAME}:${params.IMAGE_TAG}"
                // sh "docker push ${IMAGE_NAME}:${params.IMAGE_TAG}"
            }
        }
    }
}
