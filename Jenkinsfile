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
             dockerImage  = docker.build("mendelor/nodeapp6699888988998")
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
     stage('remove image')  {
       steps  {
            script {
         sh "dockerImage rmi ${env.BUILD_NUMBER}"
             
            }}}}}
  
     

     
          
