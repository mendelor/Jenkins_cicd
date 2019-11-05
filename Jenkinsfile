
 pipeline {
 agent any 
 stages {
     stage("Checkout") {
         steps {
             git 'https://github.com/mendelor/Jenkins_cicd'
         }
      } 

     stage("Build")  {
         steps  {
             script {
              dockerImage  = docker.build("mendelor/222322")
             }}}
  
      stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $registry:$BUILD_NUMBER"

             }}}}
     
     

     
          
