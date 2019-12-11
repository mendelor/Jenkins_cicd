pipeline {
    agent none

    stages {
        stage('Build') {
            agent { label 'linux' }
            steps {
                echo 'Starting the Pipeline'
                sh 'docker rm -f $(docker ps --all --quiet) || true'
                sh 'docker rmi -f $(docker images --quiet) || true'
            }
        }
    }

     stage('Build') {
       steps {
        script {
         dockerImage  = docker.build("mendel/nodeapp12345")
         }
      }
   }
}   
          
