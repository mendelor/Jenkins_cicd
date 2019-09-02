pipeline {
     agent any
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
            steps {
             input {
                message "Should we continue?"
              }
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
