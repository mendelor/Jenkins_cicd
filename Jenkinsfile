pipeline {
  agent any

   stages {
     stage('Build image') {
        steps {
            script {
            dockerImage  = docker.build("mendel/nodeapp2")
            }
         }
      }    
    stage('Deploy to Production') {
       steps {
        
               input message: 'Approve PRODUCTION Deployment?'
       
            }
            post { 
                  success {

                   echo 'Code deployed'                  
                  }
                  failure {
                   echo 'Deployment failed'
              }
            }      
          }
       }
    }
