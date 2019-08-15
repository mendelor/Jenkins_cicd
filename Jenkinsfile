  pipeline {
    agent any
      stages {
          stage('Build') {
            agent {
              docker { 
                image 'httpd:2.4' 
                label 'mydocker'
              }
          }
            steps { 
                sh 'docker build -t apchi123 . '
              }
          }

      }
  }



