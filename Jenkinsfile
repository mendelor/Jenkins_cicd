    pipeline {
      agent any

      stages {
          stage('Build') {
              steps {
                  sh 'docker build -t blahblii1111 . '
              }
          }
          stage('run') {
              steps {
                  sh ' docker run -d -p 80:80 blahblii1111 '
            }
         }
      }
  }


