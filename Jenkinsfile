pipeline {
  agent any

   stages {
     stage('Build image') {
        steps {
            script {
            dockerImage  = docker.build("mendel/nodeapp1")
            }
         }
      }    
    stage('Deploy to Production') {
       steps {
            timeout(time:5, unit:'Days'){
               input message: 'Approve PRODUCTION Deployment?'
            }

             build job: 'Deploy to Prod'
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
