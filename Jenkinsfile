pipeline {
       agent any 
         stages {
            stage('Clone repository') {
               checkout scm  
         }

            stage('build image') {
              steps { 
                 script {
                  dockerImage = docker.build("getintodevops/hellonode")

                 
             }
           }
         }
       }
     }
