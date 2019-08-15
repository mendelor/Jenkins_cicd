  pipeline {
    agent any
      stages {
          stage('Build') {
            agent {
              docker { 
                image 'httpd:2.4' 
                label 'dockerserver'
              }
          }
            steps { 
                sh 'docker build -t apchi . '
              }
          }
          stage('run') {
              steps {
                  sh ' docker run -d -p 80:80 apchi '
            }
         }
      }
  }



