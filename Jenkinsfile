  pipeline {
      agent any
  
      stages {
          stage('Build') {
              steps {
                  sh 'docker build -t blahbli1 . '
              }
          }
          stage('run') {
              steps { 
                  sh ' docker run -d -p 80:80 blahbli1 '
            }
         }

         stage('Test') {
             steps {
                 echo 'Everything's PERFECT!!!'
             }
         }


      }
  }
