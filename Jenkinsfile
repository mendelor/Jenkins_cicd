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
                dockerImage = docker.build registry + ":$BUILD_NUMBER"
               }
            }
         }
   
            stage('Test') {
              steps {
               script {
                dockerImage.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")
              }
           }
        }
   
                }
             }
  
     

     
          
