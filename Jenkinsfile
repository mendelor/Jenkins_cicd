  pipeline {
      agent any

      stages {
          stage('Build') {
              steps {
                  sh 'docker build -t blahbliiasdasd . '
              }
          }
          stage('run') {
              steps {
                  sh ' docker run -d -p 80:80 blahbliiasdasd '
            }
         }
      }
  }


