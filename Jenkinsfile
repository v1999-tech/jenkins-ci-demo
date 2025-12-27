pipline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        checkout scm
      }
    }

  stage('Run CI script') {
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
      echo "CI Pipeline completed successfully"
    }
    failure {
      echo " CI Pipeline failed"
    }
  }
}
