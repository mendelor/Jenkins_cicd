pipeline {
    agent any

    environment {
             PASS = credentials('dockerhub_pass')
      
    }
    
    stages {
        stage('Remove Docker Containers') {
            steps {
            
            sh 'docker rm -f $(docker ps --all --quiet) || true'
              }
           }
          
        stage('Remove Docker Images') {
            steps {
             sh 'docker rmi -f $(docker images --quiet) || true'
           }
        }

           stage('Build') {
               steps {
                   app = docker.build("mendel/nodeapp1")
               }
           }
           stage('run') {
               steps {
                   app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")
               }
           }
       
    }
}
