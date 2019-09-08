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
     stage('Build image') {
       steps {
         sh 'docker service create --replicas 2 -p 80:80 --name serviceName1 nginx'
      }
    }
  }
}
