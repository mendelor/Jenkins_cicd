  pipeline {
      agent none

      stages {
          stage('Build') {
            agent {
              docker { image 'php:apache' }
          }
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



