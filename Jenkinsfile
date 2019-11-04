   pipeline {
       agent { docker 'maven:3.5-alpine' }
       stages {
           stage('examle build')  {
             steps  {
               sh 'mvn --version'

             }
           stage('Run image')  {
             steps  {
               dockerImage.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")
 
             }
           } } } }
