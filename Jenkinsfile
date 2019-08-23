pipeline {
  agent any

   stages {
    stage('Build') {
       steps {
            sh 'mvn clean package'
       }
       post {
          success {
            echo 'Now Archiving...'
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

                   echo 'Code deployed                   
                  }
                  failure {
                   echo 'Deployment failed'
              }
            }      
          }
       }
    }
