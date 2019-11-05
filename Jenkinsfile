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
             dockerImage  = docker.build("mendelor/nodeapp6688898")
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
     
     

     
          
