  pipeline {
    agent any
      stages {
          stage('Build') {
            agent {
              docker { 
                image 'php:apache' 
                label 'mydocker'
              }
          }
            steps { 
                sh 'docker build -t apchi12345 . '
              }
          }

      }
  }



