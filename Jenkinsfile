  pipeline {
      agent any

      stages {
           stage('pull') {   
            // Use golang.
            agent { docker { image 'php:apache' } 
                
                  } 
           }
          stage('Build') {
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


