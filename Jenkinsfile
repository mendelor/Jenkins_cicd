  pipeline {
      agent any

      environment {
               PASS = credentials('dockerhub_pass1')
        
      }
      
      stages {
          stage('Build') {
              steps {
                  sh 'docker build -t blahblii121 . '
              }
          }
          stage('run') {
              steps {
                  sh ' docker run -d -p 80:80 blahblii121 '
            }
         }
      }
  }

