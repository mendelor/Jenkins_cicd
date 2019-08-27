pipeline {
 agent any
   stages {
     stage('Initialize') {
       steps { 
         echo 'Starting the Pipeline'
         sh 'docker rm -f $(docker ps --all --quiet) || true'
         sh 'docker rmi -f $(docker images --quiet) || true'
      }
    }  
     stage('Build') {
       steps {
        script {
         dockerImage  = docker.build("mendelor/nodeapp1")
        }
     }
  }
         
     stage('Publish') {
       when {
         branch 'master'
       }
       steps {
         withDockerRegistry([ 'https://registry.example.com', 'docker-hub-credentials' ]) {
         sh 'docker push mendelor/nodeapp1:latest'

        }
      }
    }
  }
}
