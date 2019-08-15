  pipeline {
      agent any

      stages {
          stage('Build') {
            agent { docker { image 'php:apache' } }
              steps {
                sh 'docker build -t blahblii111 . '
              }
          }
          stage('run') {
              steps {
                  sh ' docker run -d -p 80:80 blahblii111 '
            }
         }
      }
        
            post {
        always {
            // Always cleanup after the build.
                 sh ' docker rmi -f blahblii111 '
        }
     }
  }
    


