pipeline {
     agent any
       options {
        timeout(time: 1, unit: 'Minutes')
            
       stages {
         stage('Cleanup') {
           steps {
             echo 'Starting the Pipeline'
             sh 'docker rm -f $(docker ps --all --quiet) || true'
             sh 'docker rmi -f $(docker images --quiet) || true'
          }
        }
         stage('Build image') {
           steps {
            script {
             dockerImage  = docker.build("mendelor/nodeapp6698")
            }
         }
      }

         stage('Test') {
           steps {
            script {
             sh 'docker images'
           }
        }
     }

         stage('Approval') {
             input {
                message 'Should we continue?'
              }
           steps { 
              echo 'Deploying'
               
              }
           }

         stage('Run image') {
           steps {
            script {
            dockerImage.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")

             }
          }
       }
    }
 }
