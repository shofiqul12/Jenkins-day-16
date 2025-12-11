pipeline {
    agent any
    environment {
        IMAGE_NAME = "devopssteps/my-app"
    }
    stages {
        stage('build') {
            steps {
                echo "${IMAGE_NAME}"
            }
        }
        stage('test') {
            steps {
                echo 'Hello World test222'
            }    
        }
    }
}
