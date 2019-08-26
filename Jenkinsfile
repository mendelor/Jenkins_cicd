pipeline {
agent any


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
