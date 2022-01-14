pipeline {
  agent any
  environment {
    DOCKERHUB_CREDENTIALS_USR = 'narendra3425'
    DOCKERHUB_CREDENTIALS = credentials('nasingh#2022')
  }
  stages {
    stage('Build') {
      steps {
        sh './scripts/build.sh'
      }
    }
    stage('Login') {
      steps {
        sh './scripts/login.sh'
      }
    }
    stage('Push') {
      steps {
        sh './scripts/push.sh'
      }
    }
  }
  post {
    always {
      sh './scripts/logout.sh'
    }
  }
}