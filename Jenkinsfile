pipeline {
    agent any

    environment {
             PASS = credentials('dockerhub_pass')
      
    }
    
    stages {
        stage('Remove Docker Containers') {
            sh 'docker rm -f $(docker ps --all --quiet) || true'

           }
          
        stage('Remove Docker Images') {
             sh 'docker rmi -f $(docker images --quiet) || true'
           }

           stage('Build') {
               steps {
                   sh 'docker build -t blahblii . '
               }
           }
           stage('run') {
               steps {
                   sh 'docker run -d -p 80:80  blahblii'
               }
           }
       
    }
}
