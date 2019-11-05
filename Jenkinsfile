pipeline {
  environment {
    registry = "mendelor/hellonode123"
    registryCredential = ‘docker-hub-credentials’
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/mendelor/Jenkins_cicd'
      }
    }
    stage('Building image') {
      steps{
        script {
          docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
  }
}
