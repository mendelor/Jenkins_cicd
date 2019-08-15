  pipeline {
    agent { label 'mydocker' }
      stages {
          stage('Build') {
            agent {
              docker { 
                image 'httpd:2.4' 

              }
          }
            steps { 
                sh 'docker build -t apchi1 . '
              }
          }
          stage('run') {
              steps {
                  sh ' docker run -d -p 80:80 apchi1 '
            }
         }
      }
  }



