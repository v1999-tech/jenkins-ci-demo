pipeline {
    agent any

    environment {
        IMAGE_NAME = "jenkins-docker-demo"
    }

    stages {

        stage('Checkout Code') {
            steps {
               git branch: 'main', url: 'https://github.com/v1999-tech/jenkins-ci-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                  docker build -t $IMAGE_NAME:latest .
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                  docker run --rm $IMAGE_NAME:latest
                '''
            }
        }
    }

    post {
        success {
            echo 'Docker image built and tested successfully ✅'
        }
        failure {
            echo 'Docker build or run failed ❌'
        }
    }
}
