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
             dockerImage  = docker.build("mendelor/nodeapp6687878898")
            }
         }
      }

         stage('Test') {
           steps {
            script {
             sh "docker rmi $registry:$BUILD_NUMBER"
           }
        }
     }

             }
          }
  
     

     
          
