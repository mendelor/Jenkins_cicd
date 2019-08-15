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
                 sh ' docker run blahblii111 '
           }
        }
     }
 }

