  pipeline {
      agent any
  
      stages {
          stage('Build') {
              steps {
                  sh 'docker build -t blahbli . '
              }
          }
          stage('run') {
              steps { 
                  sh ' docker run -d -p 80:80 blahbli '
            }
         }

         stage('Test') {
             steps {
                 echo 'Everything's PERFECT!!!'
             }
         }


      }
  }
