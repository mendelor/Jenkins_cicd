pipeline {
 agent any
 stages {
   stage('Cloning Git') {
     steps {
       git 'https://github.com/mendelor/Jenkins_cicd'
     }
   }
   stage('Building image') {
     steps{
       script {
         dockerImage = docker.build registry + ":$BUILD_NUMBER"
       }
     }
   }
