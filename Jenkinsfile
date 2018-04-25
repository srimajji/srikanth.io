pipeline {
  agent {
      docker {
          image 'node:9-alpine'
      }
  }
  environment {
      CI = 'true'
  }
  stages {
      stage('Build') {
        steps {
            sh 'npm i now -g'
        }
      }
    stage('Deploy') {
      steps {
        withCredentials([string(credentialsId: 'NOW_TOKEN', variable: 'nowToken')]) {  
              sh "now --token $nowToken"
        }
      }
    }
  }
}
