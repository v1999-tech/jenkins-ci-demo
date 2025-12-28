pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
               checkout scm
            }
        }

        stage('Run CI Script') {
            steps {
                sh '''
                  chmod +x hello.sh
                  ./hello.sh
                '''
            }
        }
    }

    post {
        success {
            echo 'CI pipeline completed successfully ✅'
        }
        failure {
            echo 'CI pipelinefailed ❌'
        }
    }
}
