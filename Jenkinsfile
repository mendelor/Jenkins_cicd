  pipeline {
      agent any

      stages {
          stage('Build') {
              steps {
                  sh 'docker build -t blahblii11 . '
              }
          }
          stage('run') {
              steps {
                  sh ' docker run -d -p 80:80 blahblii11 '
            }
         }
      }
        
            post {
        always {
            // Always cleanup after the build.
            sh ' docker rmi -f blahblii11 '
            sh ' docker rmi -f httpd '
        }
    }
  }


