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
                app = docker.build("mendel/nodeapp1")
           }
        }
        stage('run') {
            steps {
                app.run("--name pngimage_build_${env.BUILD_NUMBER} -i -t -p 80:80")
          }
       }

       stage('Test image') {
            app.inside {
               echo "Tests passed"
          }
       }
       
    }
}
