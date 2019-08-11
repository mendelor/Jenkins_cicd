pipeline {
  agent none
  stages {
    stage('php Install') {
      agent {
        docker {
          image 'php'
        }
      }
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t php/spring-petclinic:latest .'
      }
    }
  }
}
