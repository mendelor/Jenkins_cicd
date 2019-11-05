
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
              dockerImage = docker.build registry + ":$BUILD_NUMBER"

            }}}}}
