 pipeline {
     agent { docker 'httpd:2.4' }
     stages {
         stage('examle build')  {
           steps  {
             sh 'docker rmi $registry:$BUILD_NUMBER'

           } } } }
