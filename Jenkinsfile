  pipeline {
     agent any
       options {
        timeout(time: 3, unit: 'MINUTES')
       }
       stages {
         stage('Cleanup') {
           steps {
             echo 'Starting the Pipeline'
             sh """
               docker ps -a \
                 | awk '{ print \$1,\$2 }' \
                 | grep imagename \
                 | awk '{print \$1 }' \
                 | xargs -I {} docker rm -f {}
               """
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

         stage('Deploy Prod') {
           steps {
            script {
            dockerImage.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")

             }
          }
       }
    }
 }
