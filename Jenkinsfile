pipeline {
     agent any
       stages {
     stage("Checkout") {
         steps {
             git 'https://github.com/mendelor/Jenkins_cicd'
         }
      } 
         stage('Build image') {
           steps {
            script {
             dockerImage  = docker.build("mendelor/nodeapp66878788898")
            }
         }
      }

         stage('Test') {
           steps {
            script {
             sh 'docker rmi -f $(docker images --quiet) || true'
           }
        }
     }

             }
          }
  
     

     
          
